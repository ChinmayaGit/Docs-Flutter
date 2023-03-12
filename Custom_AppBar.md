```
import 'package:cargo/widgets/color_set.dart';
import 'package:flutter/material.dart';
import 'package:get/get.dart';
```

### Default Back Action

```
aBar({required ico,required Color icoColor,required bool tIcoPre,tIco,String ?title,Widget? child}) {

  return AppBar(
    title: Text(title ?? "",style: TextStyle(color: fontOnC),),
      centerTitle: true,
      elevation: 0,
      backgroundColor: Colors.transparent,
      iconTheme: IconThemeData(color: icoColor),
  actions: [

    tIcoPre? Container(child: child):Container(),
  ],
  );
}

```

#### Adding Custom Action to back
```
aBar({required ico,required Color icoColor,required bool tIcoPre,tIco,String ?title,Widget? child}) {

  return AppBar(
    title: Text(title ?? "",style: TextStyle(color: fontOnC),),
      centerTitle: true,
      elevation: 0,
      backgroundColor: Colors.transparent,
      leading: IconButton(
        icon: Icon(
          ico,
          color: icoColor,
        ),
        onPressed: () {
          Get.back();
        },
      ),
  actions: [

    tIcoPre? Container(child: child):Container(),
  ],
  );
}
```
