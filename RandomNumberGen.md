### 4 digit number generator

1000-9999
```

  int min = 1000; 
  int max = 9999;
  var randomizer = Random();
  
  var rNum = min + randomizer.nextInt(max - min);
  print(rNum);
```

0-9999
```
  int max = 9999;
  var randomizer = Random();
  
  var rNum =randomizer.nextInt(max);
  print(rNum);
```
