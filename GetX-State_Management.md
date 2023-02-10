# Global Class

```
class dateTimeUpdater extends GetxController {
  RxString dt = "".obs;
}
```
Controller:-
```
dateTimeUpdater dtController= Get.put(dateTimeUpdater());
```
code:-
```
Obx(() => pageController.page.value = 0)
```
