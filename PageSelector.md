

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
