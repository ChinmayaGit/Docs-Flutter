# DropDown

![alt text](https://github.com/ChinmayaGit/Flutter_Info/blob/main/Pics/DropDown.png?raw=true)


### Rounded
```
var dropdownValue;
```

```
  dropDown({required int val, required String hint}) {
    return Container(
      width: MediaQuery.of(context).size.width,
      height: 50,
      margin: const EdgeInsets.all(20),
      child: DropdownButtonHideUnderline(
        child: GFDropdown(
          padding: const EdgeInsets.all(15),
          borderRadius: BorderRadius.circular(45),
          border: const BorderSide(color: Colors.black12, width: 1),
          dropdownButtonColor: Colors.white,
          value: val == 1 ? dropdownValue : dropdownValues,
          onChanged: (newValue) {
            setState(
              () {
                val == 1 ? dropdownValue : dropdownValues = newValue!;
              },
            );
          },
          items: [
            '1st',
            '2nd',
            '3rd',
          ]
              .map((value) => DropdownMenuItem(
                    value: value,
                    child: Text(value),
                  ))
              .toList(),
          hint: Text(
            hint,
            textAlign: TextAlign.center,
          ),
        ),
      ),
    );
  }

```

### Custom Widget Stateless DropDown

```
  List listOne=["Select Vendor","abc","xyz"];
  
  DropDownOneCreate ddController = DropDownOneCreate();
```

Class
```
class DropDownOneCreate extends GetxController {
final selected = "Select Vendor".obs;
void setSelected(value){
    selected.value = value;
  }
}
```

Widget
```
dropDown(hint: "Select Vendor",context: context,controller: ddController,list: listOne),
```
```
dropDown(
    {required String hint, required context, controller, required List list}) {
  return Obx(
    () => Container(
      width: MediaQuery.of(context).size.width,
      height: 50,
      margin: const EdgeInsets.all(20),
      child: DropdownButtonHideUnderline(
        child: GFDropdown(
          padding: const EdgeInsets.all(15),
          borderRadius: BorderRadius.circular(45),
          border: const BorderSide(color: Colors.black12, width: 1),
          dropdownButtonColor: Colors.white,
          value: controller.selected.value,
          onChanged: (newValue) {
            controller.setSelected(newValue.toString());
          },
          items: list.map((selectedType) {
            return DropdownMenuItem(
              child: Text(
                selectedType,
              ),
              value: selectedType,
            );
          }).toList(),
          hint: Text(
            hint,
            textAlign: TextAlign.center,
          ),
        ),
      ),
    ),
  );
}

```

