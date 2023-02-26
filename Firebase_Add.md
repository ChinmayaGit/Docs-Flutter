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
