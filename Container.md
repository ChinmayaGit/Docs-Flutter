# Rounded Border
```
decoration: BoxDecoration(
         border: Border.all(
         color: Colors.white,
      ),
   borderRadius: BorderRadius.all(Radius.circular(20))
),
```

# Rounded Container
```
decoration: ShapeDecoration(
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(18.0),
        ),color: Colors.white
      ),
```

# Half Rounded Container

```
    decoration: const ShapeDecoration(
                            shape: RoundedRectangleBorder(
                              borderRadius: BorderRadius.only(
                                topLeft: Radius.circular(50.0),
                                topRight: Radius.circular(50.0),
                              ),
                            ),
    color: Colors.white,
),
```
