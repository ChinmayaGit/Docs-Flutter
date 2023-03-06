## Map List

```dart
List<Map<String, String>> allTotal = [];
```

Add Items to List
```dart
  allTotal.add({
            "price": "${double.parse(miscellaneousController.text)}",
            "type": "miscellaneous",
            "id": rNum.toString()
          });
```

getItem
```
allTotal[index]["type"]
```
