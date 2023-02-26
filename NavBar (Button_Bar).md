
# NavBar-1

![alt text](https://raw.githubusercontent.com/ChinmayaGit/Flutter_Info/main/Pics/Nav_Bar-1.png)

```
    Center(
          child: Stack(
            alignment: Alignment.center,
            children: [
              Container(
                height: 50,
                width: Get.width / 1.7,
                decoration: ShapeDecoration(
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(50.0),
                    ),
                    color: Colors.white),
              ),
              Row(
                children: [
                  Expanded(child: SizedBox()),
                  Expanded(
                    child: GestureDetector(
                        onTap: () {}, child: Icon(Icons.arrow_back_ios_sharp)),
                  ),
                  Expanded(
                    child: Center(
                      child: Container(
                        decoration: ShapeDecoration(
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(50.0),
                            ),
                            color: Color(0xffe5e5e5)),
                        height: 65,
                        width: 65,
                        child: Padding(
                          padding: const EdgeInsets.all(8.0),
                          child: Center(child: Text("1st")),
                        ),
                      ),
                    ),
                  ),
                  Expanded(
                    child: Icon(Icons.arrow_forward_ios_sharp),
                  ),
                  Expanded(child: SizedBox()),
                ],
              )
            ],
          ),
        ),
```

# NavBar-1.1

![alt text](https://raw.githubusercontent.com/ChinmayaGit/Flutter_Info/main/Pics/Nav_Bar-1.1.png)


```
backgroundColor:-Color(0xff272a50)
```

```
 Center(
          child: Stack(
            alignment: Alignment.center,
            children: [
              Container(
                height: 50,
                width: Get.width / 1.7,
                decoration: ShapeDecoration(
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(50.0),
                    ),
                    color: Colors.white),
              ),
              Row(
                children: [
                  Expanded(child: SizedBox()),
                  Expanded(
                    child: GestureDetector(
                        onTap: () {}, child: Icon(Icons.arrow_back_ios_sharp)),
                  ),
                  Expanded(
                    child: Center(
                      child: Container(
                        height: 70,
                        width: 70,
                        decoration: ShapeDecoration(
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.circular(50.0),
                            ),
                            color: Color(0xff272a50),),
                        child: Padding(
                          padding: const EdgeInsets.all(8.0),
                          child: Container(
                            decoration: ShapeDecoration(
                                shape: RoundedRectangleBorder(
                                  borderRadius: BorderRadius.circular(50.0),
                                ),
                                color: Color(0xffe5e5e5)),

                            child: Padding(
                              padding: const EdgeInsets.all(8.0),
                              child: Center(child: Text("1st")),
                            ),
                          ),
                        ),
                      ),
                    ),
                  ),
                  Expanded(
                    child: Icon(Icons.arrow_forward_ios_sharp),
                  ),
                  Expanded(child: SizedBox()),
                ],
              )
            ],
          ),
        ),
```

# NavBar-2

![alt text](https://raw.githubusercontent.com/ChinmayaGit/Flutter_Info/main/Pics/Nav_Bar-2.png)

```
    Center(
          child: Stack(
            alignment: Alignment.bottomCenter,
            children: [
              Container(
                height: 50,
                width: Get.width / 1.7,
                decoration: ShapeDecoration(
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(18.0),
                    ),
                    color: Colors.white),
              ),
              Row(
                children: [
                  Expanded(child: SizedBox()),
                  Expanded(
                    child: GestureDetector(
                        onTap: () {

                        }, child: Icon(Icons.mode_edit_outline_rounded)),
                  ),
                  Expanded(
                    child: Center(
                      child: GestureDetector(
                        onTap: (){

                        },
                        child: Container(
                          decoration: ShapeDecoration(
                              shape: RoundedRectangleBorder(
                                borderRadius: BorderRadius.circular(50.0),
                              ),
                              color: Color(0xffe5e5e5)),
                          height: 55,
                          width: 55,
                          child: Padding(
                            padding: const EdgeInsets.all(8.0),
                            child: Icon(Icons.add_circle_outlined),
                          ),
                        ),
                      ),
                    ),
                  ),
                  Expanded(
                    child: Icon(Icons.delete_forever),
                  ),
                  Expanded(child: SizedBox()),
                ],
              )
            ],
          ),
        ),
```
# NavBar-3

![alt text](https://raw.githubusercontent.com/ChinmayaGit/Flutter_Info/main/Pics/Nav_Bar_3.png)

Controller
```
  PagesSelectorCreate pageController = Get.put(PagesSelectorCreate());

```
Class
```
class PagesSelectorCreate extends GetxController {
  RxInt page = 0.obs;
}
```
Widget
```
 selectPage() {
    return Padding(
      padding: const EdgeInsets.all(8.0),
      child: Container(
        height: 50,
        decoration: ShapeDecoration(
            shape: RoundedRectangleBorder(
              borderRadius: BorderRadius.circular(30.0),
            ),
            color: Colors.white),
        child: Row(
          children: [
            SizedBox(
              width: 2,
            ),
            Expanded(
              child: GestureDetector(
                onTap: () {
                  pageController.page.value = 0;
                },
                child: Container(
                  height: 45,
                  decoration: ShapeDecoration(
                    shape:const RoundedRectangleBorder(
                      borderRadius: BorderRadius.only(
                        topLeft: Radius.circular(30.0),
                        bottomLeft: Radius.circular(30.0),
                      ),
                    ),
                    color: pageController.page.value==0?Colors.white:Colors.black,
                  ),
                  child: Center(
                    child: Text(
                      "Vendor",
                      style: TextStyle(color: pageController.page.value==0?Colors.black:Colors.white),
                    ),
                  ),
                ),
              ),
            ),
            SizedBox(
              width: 2,
            ),
            Expanded(
              child: GestureDetector(
                onTap: () {
                  pageController.page.value = 1;
                },
                child: Container(
                  height: 45,
                  color: pageController.page.value==1?Colors.white:Colors.black,
                  child: Center(
                      child: Text(
                    "Items",
                    style: TextStyle(color: pageController.page.value==1?Colors.black:Colors.white),
                  )),
                ),
              ),
            ),
            SizedBox(
              width: 2,
            ),
            Expanded(
              child: GestureDetector(
                onTap: () {
                  pageController.page.value = 2;
                },
                child: Container(
                  height: 45,
                  decoration: ShapeDecoration(
                    shape: const RoundedRectangleBorder(
                      borderRadius: BorderRadius.only(
                        topRight: Radius.circular(30.0),
                        bottomRight: Radius.circular(30.0),
                      ),
                    ),
                    color: pageController.page.value==2?Colors.white:Colors.black,
                  ),
                  child: Center(
                      child: Text(
                    "Maps",
                    style: TextStyle(color: pageController.page.value==2?Colors.black:Colors.white),
                  )),
                ),
              ),
            ),
            SizedBox(
              width: 2,
            ),
          ],
        ),
      ),
    );
  }
```
