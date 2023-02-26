Post/Get Data

```
  Future submitDetails(
    String organization,
    String orgId,
    bool collegeStatus,
    String year,
    String area,
    String department,
  ) async {
    final uri =
        Uri.parse(baseUrl+'individual/profile/update');
    final headers = {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer ${box.read('token')}',
    };
    Map<String, dynamic> body = {
      'organization': organization,
      'orgId': orgIdState != "null" ? orgId : false,
      'collegeStatus': collegeStatus,
      'year': year,
      'area': area,
      'department': department,
      // 'dob': "0000/00/00",
      // 'about': "Hi i am a new User",
      // 'profileImage':"https://i.imgur.com/C8ay3a0.png",
    };
    String jsonBody = json.encode(body);
    final encoding = Encoding.getByName('utf-8');

    http.Response response = await http.post(
      uri,
      headers: headers,
      body: jsonBody,
      encoding: encoding,
    );
    print(response.statusCode);
    jsonResponse = json.decode(response.body);
  }
```
## Nested
### offline example data:
```
var json = {
    "destination_addresses": [
      "GVHF+HQC, Station Rd, Agarkar Nagar, Pune, Maharashtra 411001, India"
    ],
    "origin_addresses": [
      "GVC4+5M9, Dhayari, Shobhapur, Kasba Peth, Pune, Maharashtra 411011, India"
    ],
    "rows": [
      {
        "elements": [
          {
            "distance": {"text": "1.5 mi", "value": 2458},
            "duration": {"text": "12 mins", "value": 696},
            "status": "OK"
          }
        ]
      }
    ],
    "status": "OK"
  }; 

var myMap = Map<String, dynamic>.from(json);
print(myMap["rows"][0]["elements"][0]["duration"]["text"]);

```
### online api fetch data:

```
Response response=await dio.get("https://maps.googleapis.com");
print(response.data);
var myMap = Map<String, dynamic>.from(response.data);
print(myMap["rows"][0]["elements"][0]["duration"]["text"]);
```
