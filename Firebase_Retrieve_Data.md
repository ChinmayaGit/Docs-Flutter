### Add this two lines to show page turn blank in (Nested column or row)

Grid View, ListView(),ListView.builder()
```
shrinkWrap: true,
physics: NeverScrollableScrollPhysics(),
```
Above Not Working try This

```
Flexible(GridView.builder())
```


### Firebase get date and time
```
snapshot.data!.docs[index]["time"].toDate().toString()
```


### Firebase get date and time
```
snapshot.data!.docs[index]["time"].toDate().toString()
```

Firebase get date and time (intl: ^0.17.0 (Needed))
```
(intl: ^0.17.0) Needed

DateFormat.yMMMd().add_jm().format(snapshot.data!.docs[index]["time"].toDate()).toString()
```
---
# Conditions

OrderBy
```
.orderBy('time',descending: true)
```

Where
```
.where('status', isEqualTo: rideType)
```

Limit
```
.limit(10)
```
---

# Stream Builder


## List View
```
StreamBuilder(
        stream: FirebaseFirestore.instance.collection('vehicles').snapshots(),
        builder: (BuildContext context, AsyncSnapshot<QuerySnapshot> snapshot) {
          if (!snapshot.hasData)
            return const Center(
              child: CircularProgressIndicator(),
            );
          return Padding(
            padding: const EdgeInsets.only(left: 18.0, right: 18.0),
            child: Column(
              children: [
                ListView.builder(
                  shrinkWrap: true,
                  physics: NeverScrollableScrollPhysics(),
                  itemCount: snapshot.data!.docs.length,
                  itemBuilder: (context, index) {
                    return GestureDetector(
                      onTap: () {
                      },
                      child: Container(
                        height: 50,
                        child: Row(
                          children: [
                            Expanded(
                                flex: 1,
                                child: Center(
                                    child: Text((index + 1).toString()))),
                            Expanded(
                                flex: 2,
                                child: Center(
                                    child: Text(
                                        snapshot.data!.docs[index]["owner"]))),
                            Expanded(
                                flex: 2,
                                child: Center(
                                    child: Text(
                                        snapshot.data!.docs[index]['phone']))),
                          
                          ],
                        ),
                      ),
                    );
                  },
                ),
              ],
            ),
          );
        },
      ),
```


## List View (V2)
```
class Pageo extends StatefulWidget {
  @override
  _PageoState createState() => _PageoState();
}

class _PageoState extends State<Pageo> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: StreamBuilder(
        stream: FirebaseFirestore.instance.collection('Address').snapshots(),
        builder: (BuildContext context, AsyncSnapshot<QuerySnapshot> snapshot) {
          if (!snapshot.hasData) return Text("There is no expense");
          return ListView(children: getExpenseItems(snapshot));
        },
      ),
    );
  }

  getExpenseItems(AsyncSnapshot<QuerySnapshot> snapshot) {
    return snapshot.data.docs
        .map(
          (doc) => ListTile(
            title: Text(doc["name"]),
            subtitle: Column(
              children: <Widget>[
                Text(doc['Address']),
                Text(doc['Phone no.']),
                Text(doc['prodname']),

              ],
            ),
          ),
        )
        .toList();
  }
}
```


## ListView.builder()
```
ListView.builder(
                  shrinkWrap: true,
                  physics: NeverScrollableScrollPhysics(),
                  itemCount: snapshot.data!.docs.length,
                  itemBuilder: (context, index) {
                    return Container(
                      height: 50,
                      child:
                    Row(
                        children: [
                           Expanded(
                              flex: 1, child: Center(child:Text((index+1).toString()))),
                          Expanded(
                              flex: 2,
                              child: Center(child: Text(snapshot.data!.docs[index]["owner"]))),
                     
                        ],
                      ),
                    );
                  },
                ),
```


## Grid View

```
height=gridDelegate: SliverGridDelegateWithFixedCrossAxisCount
(crossAxisCount: 2,childAspectRatio: MediaQuery.of(context).size.width /
                (MediaQuery.of(context).size.height ),),

      StreamBuilder(
              stream: FirebaseFirestore.instance.collection('drivers').snapshots(),
              builder: (BuildContext context, AsyncSnapshot<QuerySnapshot>snapshot) {
                if (!snapshot.hasData)
                  return Text("There is no expense");
                return GridView.builder(
                    gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(crossAxisCount: 3),
                    itemCount: snapshot.data!.docs.toList().length,
                    padding: EdgeInsets.all(2.0),
                    itemBuilder: (BuildContext context, int index) {
                      return Container(
                        child: Image.network(
                          snapshot.data!.docs.toList()[index]["link"],
                          fit: BoxFit.cover,
                        ),
                        padding: EdgeInsets.all(2.0),
                      );
                    });
              },
            ),
```
## Firebase Single Doc

```
StreamBuilder(
      stream: Firestore.instance.collection('COLLECTION_NAME').document('TESTID1').snapshots(),
      builder: (context, snapshot) {
        if (!snapshot.hasData) {
          return new Text("Loading");
        }
        var userDocument = snapshot.data;
        return new Text(userDocument["name"]);
      }
  );
```
---

# Fetch Data at Initialization

## Fetch all data in List

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


## OR

## Fetch all data in var
```
var pricingData;

Future<void> pricingDataGet() async {
  QuerySnapshot querySnapshot = await FirebaseFirestore.instance.collection("pricing").get();
  pricingData = querySnapshot.docs;
  print(pricingData[index]['type']);
}
```


## Fetch only single list Data
```
@override
  void initState() {
    // TODO: implement initState
    super.initState();
    vehicleData();
  }
  List vehicles = [];
  bool dataFetched=false;
  vehicleData()async{
    FirebaseFirestore.instance
        .collection("vehicles")
        .snapshots()
        .listen((event) {
      for (var i = 0; i < event.docs.length; i++) {
        vehicles.add(event.docs[i]["vno"].toString());
      }
    });

    Timer(Duration(seconds: 2), () {
      setState(() {

      });
      dataFetched=true;
    });

  }
```


## Reference
```
bool isFetching=false;
List<String> dataList=[];

@override
void initState() {
super.initState();

getGroupsData();
}

getGroupsData() {
setState(() {
   isFetching= true;
});

databaseReference
    .collection("profile")
    .getDocuments()
    .then((QuerySnapshot snapshot) {
    snapshot.documents.forEach((f) => dataList.add[f.data["name"]));

   setState(() {
      isFetching= false;
   });
  });
}

@override
  Widget build(BuildContext context) {
    return Scaffold(
    body: Center(
    child : isFetching ?
            CircularProgressIndictaor()
            : dataList!=null && dataList.length >0 
            ? ListView.builder(
                  itemCount: snapshot.data.length,
                  itemBuilder: (BuildContext context, int index) {
                               return Text(dataList[index]);
                               }
                  )
            : Text("No Data"),
      )
    );
}
```


## Get single data (collection)
```
var querySnapshot = await FirebaseFirestore.instance
        .collection('users')
        .doc(box.read('uid'))
        .collection('payments').doc(ridesData["cfLink"])
        .get();

print(querySnapshot.data()!["totalAmount"]);
```
## Get single data (doc)
```
DocumentSnapshot variable = await FirebaseFirestore.instance
        .collection('drivers')
        .doc(widget.driverUid)
        .get();
        
```


## Get Length
```
firestoreInstance.collection("users")
                    .doc(
                        "${Provider.of<UserProvider>(context, listen: false).user.uid}")
                    .collection("cart")
                    .snapshots()
                    .listen((event) {
                  for (var i = 0; i < event.docs.length; i++) {
                    print(event.docs[i]["product_subtotal"]);
                    pricecal += event.docs[i]["product_subtotal"];
                  }
                  print(pricecal);

                  return pricecal;
                });
```


## Check if collection or doc exists
```
final snapshot = await  FirebaseFirestore.instance.collection("USERS")
.doc(FirebaseAuth.instance.currentUser!.uid).collection("TOKEN").get();
    if (snapshot.docs.length == 0) {
      print("Not Exists");
      FirebaseFirestore.instance
          .collection('USERS')
          .doc(FirebaseAuth.instance.currentUser!.uid)
          .collection('TOKEN')
          .doc(deviceToken)
          .set({
        'TOKEN': deviceToken,
        'PLATFORM': Platform.operatingSystem,
      });
    }else{}
```


## Firebase Getting Lat Lan

```
List<LatLng> dropAirLat = [];
  List<LatLng> dropTrainLat = [];

  // bool dataFetched=false;
  vehicleData() async {
    FirebaseFirestore.instance
        .collection("location")
        .snapshots()
        .listen((event) {
      for (var i = 0; i < event.docs.length; i++) {
        if (event.docs[i]["type"].toString() == "airport") {
          dropAirLoc.add(event.docs[i]["name"].toString());
          dropAirLat.add(LatLng(
            event.docs[i]["location"].latitude,
            event.docs[i]["location"].longitude,
          ));
        } else {
          dropTrainLoc.add(event.docs[i]["name"].toString());
          dropTrainLat.add(LatLng(
            event.docs[i]["location"].latitude,
            event.docs[i]["location"].longitude,
          ));
        }
      }
    });
```
---
# Links:-

### GetX Firebase

https://medium.com/@CodingWithImran/cloud-firestore-crud-operation-with-getx-in-flutter-2b429359c37








