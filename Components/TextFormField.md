Basic
-----
```
TextEditingController _nameController = TextEditingController();
String name="";

Padding(
            padding: const EdgeInsets.all(8.0),
            child: TextFormField(
              autofocus: true,
              controller: _nameController,
              validator: (value) {
                if (value!.isEmpty)
                  return 'This field cannot be empty';
                return null;
              },
              // onSaved: (value) =>
              // nameEditor = value.toString(),
              decoration:const InputDecoration(
                  hintText:
                  'Full name (First and Last name)',
                  labelText: 'Name'),
            ),
          ),
```



To show
-------
```
Text(_nameController.text);
```

To Clear
--------
```
clean
  setState(() {
    _nameController.clear();
  });
```

Rounded
-------

declaration:
```
final TextEditingController _nameController = TextEditingController();
```

calling:
```
textF(const Icon(Icons.person),"Password","Password",_nameController),
```

function:
```
  customTextField(Icon icon, String lName, String hName,
      TextEditingController controllers) {
    return Padding(
      padding: const EdgeInsets.all(8.0),
      child: Container(
        padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 0),
        decoration: BoxDecoration(
          color: Colors.blue[50],
          borderRadius: BorderRadius.circular(29),
        ),
        child: TextFormField(
          autofocus: false,
          controller: controllers,
          validator: (value) {
            if (value!.isEmpty) return 'This field cannot be empty';
            return null;
          },
          decoration: InputDecoration(
            border: InputBorder.none,
            focusedBorder: InputBorder.none,
            enabledBorder: InputBorder.none,
            errorBorder: InputBorder.none,
            disabledBorder: InputBorder.none,
            icon: icon,
            hintText: hName,
            labelText: lName,
          ),
        ),
      ),
    );
  }
```