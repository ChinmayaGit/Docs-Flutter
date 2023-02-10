# DropDown

![alt text](https://github.com/ChinmayaGit/Flutter_Info/blob/main/Pics/DropDown.png?raw=true)

```
var dropdownValue;
```
Rounded
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
