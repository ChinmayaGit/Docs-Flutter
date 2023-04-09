packages
```
flutter pub add flutter_image_compress

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

    if (img != null) {
      final File imageFile = File(img.path);
      final compressedImageData = await FlutterImageCompress.compressWithFile(
        imageFile.path,
        minHeight: 256,
        minWidth: 256,
        quality: 80,
        format: CompressFormat.png,
      );
      final File compressedImageFile = File(imageFile.path)
        ..writeAsBytesSync(compressedImageData!);
      var selectedImageTwo = XFile(compressedImageFile.path);
      setState(() {
        image = selectedImageTwo;
      });
    }

  }

```
