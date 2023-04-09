packages
```
flutter pub add image
flutter pub add image_picker
flutter pub add path_provider

```
import
```
import 'package:image/image.dart' as Im;
import 'dart:math' as Math;
```

```
  final ImagePicker picker = ImagePicker();
  XFile? image;

```

PickImage
```
Center(
                          child: GestureDetector(
                            onTap: () {
                              getImage(ImageSource.gallery);
                            },
                            child: Container(
                              height: 100,
                              width: 100,
                              child: Image.asset("assets/addImage.png"),
                            ),
                          ),
                        ),
```
image Compress
```
  Future getImage(ImageSource media) async {
    var img = await picker.pickImage(source: media);
    var selectedImage = File(img!.path);
    final tempDir = await getTemporaryDirectory();
    final path = tempDir.path;
    int rand = new Math.Random().nextInt(10000);

    Im.Image? imageTwo = Im.decodeImage(selectedImage.readAsBytesSync());
    Im.Image smallerImage = Im.copyResize(imageTwo!,
        width: 250,
        height: 250); // choose the size here, it will maintain aspect ratio

    var compressedImage = new File('$path/img_$rand.jpg')
      ..writeAsBytesSync(Im.encodeJpg(imageTwo, quality: 85));
    var selectedImageTwo = XFile(compressedImage.path);
    setState(() {
      image = selectedImageTwo;
    });
  }
```
