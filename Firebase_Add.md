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

## Add Map Data
```
 Firestore.instance.collection('users').document(some_docID).set({
      'map1': {
        'key1': 'value1',
        'key2': 'value2',
      }});
```
## Add Nested Map Data
```
  FirebaseFirestore.instance
                .collection("bookings")
                .doc(widget.id)
                .update({
              "bill": {
                "1232": {
                  "name": "Toll",
                  "price": "${double.parse(tollController.text)}",
                  "type": "toll",
                }
              }
            });
```
