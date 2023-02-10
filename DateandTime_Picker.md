# DateandTime_Picker

# Types of data
![alt text](https://raw.githubusercontent.com/ChinmayaGit/Flutter_Info/main/Pics/DateTime.png?token=GHSAT0AAAAAAB6TDPBZW3GDG6YLJKRYGSISY7GTMPA)


# Packages

Link:-https://pub.dev/packages/flutter_datetime_picker
```
flutter_datetime_picker: ^1.5.1
```




Initialization:-
```
DateTimeUpdater dtController= Get.put(DateTimeUpdater());
```
controller:-
```
class DateTimeUpdater extends GetxController {
  RxString dt = "".obs;
}
```

# Select Date

```
Center(
          child: Container(
            decoration: BoxDecoration(
                border: Border.all(
                  color: Colors.white,
                ),
                borderRadius: BorderRadius.all(Radius.circular(20))
            ),
            child:Obx(()=> TextButton(
              onPressed: () {
                DatePicker.showDatePicker(context,
                  showTitleActions: true,
                  minTime: DateTime(2023, 1, 1),
                  maxTime: DateTime(2025, 12, 31), onChanged: (date) {
                    print('change $date');
                  }, onConfirm: (date) {

                    dtController.dt.value= "${date.day}/${date.month}/${date.year}";
                    print('confirm $date');
                  }, currentTime: DateTime.now(),);
              },
              child: dtController.dt.value==""? Text(
                'Select Date',
                style: TextStyle(color: Colors.white),
              ):Text(
                dtController.dt.value,
                style: TextStyle(color: Colors.white),
              ),),),
          ),
        ),
```

# Select Time
```
 Center(
          child: Container(
            decoration: BoxDecoration(
                border: Border.all(
                  color: Colors.white,
                ),
                borderRadius: BorderRadius.all(Radius.circular(20))
            ),
            child:Obx(()=>  TextButton(
              onPressed: () {
                DatePicker.showTime12hPicker(context, showTitleActions: true,
                   onConfirm: (date) {
                      dtController.dt.value="Time-${date.hour}:${date.minute}";
                      print('confirm $date');
                    }, currentTime: DateTime.now());
              },
                child: dtController.dt.value==""? Text(
                  'Select Date',
                  style: TextStyle(color: Colors.white),
                ):Text(
                  dtController.dt.value,
                  style: TextStyle(color: Colors.white),
                 ),),),
          ),
        ),

```
# Select Date And Time
```
  Center(
          child: Container(
            decoration: BoxDecoration(
                border: Border.all(
                  color: Colors.white,
                ),
                borderRadius: BorderRadius.all(Radius.circular(20))
            ),
            child:Obx(()=>  TextButton(
              onPressed: () {
                DatePicker.showDateTimePicker(context, showTitleActions: true,
                    onChanged: (date) {
                      dtController.dt.value="${date.day}/${date.month}/${date.year}_${date.hour}:${date.minute}";
                      print('confirm $date');
                    }, currentTime: DateTime.now());
              },
                child: dtController.dt.value==""? Text(
                  'Select Date',
                  style: TextStyle(color: Colors.white),
                ):Text(
                  dtController.dt.value,
                  style: TextStyle(color: Colors.white),
                ),),),
          ),
        ),
```
