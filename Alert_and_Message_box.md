# Fluttertoast

```
fluttertoast: ^8.1.1
```

```
import 'package:fluttertoast/fluttertoast.dart';

Fluttertoast.showToast(
        msg: "This is Center Short Toast",
        toastLength: Toast.LENGTH_SHORT,
        gravity: ToastGravity.CENTER,
        timeInSecForIosWeb: 1,
        backgroundColor: Colors.red,
        textColor: Colors.white,
        fontSize: 16.0
    );
   
```   
# ShowDialog  
```
    showDialog(
                            context: context,
                            builder: (BuildContext context) {
                              // return object of type Dialog
                              return AlertDialog(
                                shape: RoundedRectangleBorder(
                                  borderRadius: BorderRadius.circular(20.0),
                                ),
                                title: new Text(
                                  "Are You Sure You Want to Cancle It!",
                                  textAlign: TextAlign.center,
                                ),
                                actions: <Widget>[
                                  Center(
                                    child: GestureDetector(
                                        onTap: () {
                                          setState(() {
                                            billList.removeAt(index);

                                          });
                                          Get.back();
                                        },
                                        child: Container(
                                          height: 60,
                                          width: 200,
                                          decoration: ShapeDecoration(
                                              shape: RoundedRectangleBorder(
                                                borderRadius:
                                                    BorderRadius.circular(18.0),
                                              ),
                                              color: Colors.green),
                                          child: Center(
                                              child: Text(
                                            "Yes",
                                            style: TextStyle(
                                                color: Colors.white,
                                                fontSize: 20),
                                          )),
                                        )),
                                  ),
                                  SizedBox(
                                    height: 10,
                                  ),
                                  Center(
                                    child: GestureDetector(
                                        onTap: () {
                                          Get.back();
                                        },
                                        child: Container(
                                          height: 60,
                                          width: 200,
                                          decoration: ShapeDecoration(
                                              shape: RoundedRectangleBorder(
                                                borderRadius:
                                                    BorderRadius.circular(18.0),
                                              ),
                                              color: Colors.red),
                                          child: Center(
                                              child: Text(
                                            "No",
                                            style: TextStyle(
                                                color: Colors.white,
                                                fontSize: 20),
                                          )),
                                        )),
                                  ),
                                  // FlatButton(
                                  //   child: new Text("Close"),
                                  //   onPressed: () {
                                  //     Navigator.of(context).pop();
                                  //   },
                                  // ),
                                ],
                              );
                            },
                          );
                          
 ```
    
