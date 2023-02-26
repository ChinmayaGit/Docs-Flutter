
### Get List Data


```
  List billList = [];
  
  late CollectionReference collectionRef;
  
    @override
  void initState() {
    super.initState();
    collectionRef = FirebaseFirestore.instance
        .collection("users")
        .doc(widget.uid)
        .collection("bill");
    getData();
  }
```

Add all data single list
```
 Future getData() async {
    try {
      await collectionRef.get().then((querySnapshot) {
        for (var result in querySnapshot.docs) {
          billList.add(result.data());
        }
      });
      return billList;
    } catch (e) {
      debugPrint("Error - $e");
      return null;
    }
  }
```

Get it
```
billList[0]["type"]
```
