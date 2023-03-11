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
## Delete Data

```
Firestore.instance.collection("chats").document("ROOM_1")  
    .collection("messages").document(snapshot.data.documents[index]["id"])
    .delete();
```

Delete collection data

```
      FirebaseFirestore.instance
          .collection("bookings")
          .doc(widget.id)
          .collection("bill")
          .snapshots()
          .forEach((element) {
        for (QueryDocumentSnapshot snapshot in element.docs) {
          snapshot.reference.delete();
        }
      });
```
