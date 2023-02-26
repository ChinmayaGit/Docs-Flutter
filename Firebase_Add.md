## Add Data

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
## Set Data

```
    FirebaseFirestore.instance
                .collection("messages").doc(widget.id)
                .set({
              "name": "Toll",
              "price": "${double.parse(tollController.text)}",
              "type": "toll",
            });
```
## Update Data

```
 FirebaseFirestore.instance
                .collection("messages").doc(widget.id)
                .update({
              "name": "Toll",
              "price": "${double.parse(tollController.text)}",
              "type": "toll",
            });
```
