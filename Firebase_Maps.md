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
## fetch
```
  QuerySnapshot querySnapshot = await FirebaseFirestore.instance.collection("user").get();
  print(querySnapshot.docs[index]["name"]["id"].toString());
```
