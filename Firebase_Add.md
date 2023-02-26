Add data

```

final _firestore = FirebaseFirestore.instance;
                           _firestore
                              .collection("messages")
                              .add({
                            "text": messageText,
                            "sender": loggedInUser.email,
                            "time": DateTime.now(),
                          });
```
set data

```
    FirebaseFirestore.instance
                .collection("messages").doc(widget.id)
                .set({
              "name": "Toll",
              "price": "${double.parse(tollController.text)}",
              "type": "toll",
            });
```
