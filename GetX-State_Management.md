# Global Class

```
class Updater extends GetxController {
  RxString dt = "".obs;
}
```
get value:-
```
Updater dtController= Get.put(Updater());

Obx(() => Text("pageController.page.value"))
```
add value:-
```
Updater dtController= Get.put(Updater());

tpController.fetchData.value=true;
```
