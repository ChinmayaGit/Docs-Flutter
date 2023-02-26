Array Data

```
      List<Map> yourItemList=[
        {
          'product_name': item.product_name,
          'product_price': item.product_price,
          'product_image': item.product_image,
          'product_quantity': item.product_quantity,
          'station_id': item.station_id,
          'user': user.uid,
          'product_id': item.product_id,
          'product_subtotal': item.product_price * item.product_quantity,
        },
      ];
```
### ADD
```
 _firestore
              .collection("users").doc(user.uid).collection("cart").doc(item.station_id)
              .set({
            "productList": FieldValue.arrayUnion(yourItemList),

          }).then((value){
              Navigator.pop(context);
          });
```
### Update
```
       _firestore
              .collection("users").doc(user.uid).collection("cart").doc(item.station_id)
              .update({
            "productList": FieldValue.arrayUnion(yourItemList),
          }).then((value){
            Navigator.pop(context);
        });
```

### Fetch Data
```
 _firestore
        .collection("users").doc(user.uid).collection("cart").doc(item.station_id).get().then((value){
      if(value.data()!=null){
        print(value.data()['']);
      }
    });
```
## Fetch Data By StreamBuilder()
```
getExpenseItems(
      AsyncSnapshot<DocumentSnapshot<Map<String, dynamic>>> snapshot) {
    return snapshot.data
        .get("productList")
        .map<Widget>(
          (doc) => ListTile(
            title: Row(
              children: <Widget>[,
                Expanded(
                  flex: 2,
                  child: Container(
                    height: 100,
                    decoration: ShapeDecoration(
                        shape: RoundedRectangleBorder(
                          borderRadius: new BorderRadius.only(
                            bottomLeft: const Radius.circular(30.0),
                            topRight: const Radius.circular(30.0),
                          ),
                        ),
                        color: Colors.deepOrangeAccent),
                    child: Column(
                      mainAxisAlignment: MainAxisAlignment.center,
                      children: [
                        Padding(
                          padding: const EdgeInsets.all(4.0),
                          child: Text(
                            doc["productQuantity"].toString(),
                            style: TextStyle(color: Colors.white),
                          ),
                        ),

                      ],
                    ),
                  ),
                ),
              ],
            ),
          ),
        )
        .toList();
  }


          Container(
            height: MediaQuery.of(context).size.height / 1.5,
            width: MediaQuery.of(context).size.width,
            child: StreamBuilder<DocumentSnapshot<Map<String, dynamic>>>(

              stream: Provider.of<Cart>(context).fetchByStream(),
              builder: (BuildContext context,
                  AsyncSnapshot<DocumentSnapshot<Map<String, dynamic>>>
                      snapshot) {
                if (!snapshot.hasData) return Text("There is no expense");

                // print(snapshot.data.get('productList'));

                return ListView(
                    children: getExpenseItems(snapshot)
                );
              },
            ),
          ),
```
