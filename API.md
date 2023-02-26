Post/Get Data

```
  var jsonResponse;
  
  String baseUrl="https://us/app";

  Future submitDetails() async {
    final uri = Uri.parse(baseUrl + '/generateBill');
    final headers = {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer token',
    };
    Map<String, dynamic> body = {
      "customerNumber": widget.num,
      "customerEmail": widget.email == "Not Provided" ? null : widget.email,
      "customerName": widget.name,
      "amount": totalFare + total,
      "purpose": "ride end",
      "customerId": widget.uid,
      "bookingId": widget.id,
    };
    String jsonBody = json.encode(body);
    final encoding = Encoding.getByName('utf-8');

    http.Response response = await http.post(
      uri,
      headers: headers,
      body: jsonBody,
      encoding: encoding,
    );
    jsonResponse = json.decode(response.body);

    var myMap = Map<String, dynamic>.from(jsonResponse);
  }
```
