Dart Sdk Path:
--------------

D:\Softwares\Android Studio\Flutter\flutter\bin\cache\dart-sdk

Java Sdk path for (SHA256): +  (SHA1): 
--------------------------------------
C:\Program Files\Java\jre1.8.0_131\bin

For (All):
```
cd android
./gradlew signingReport
```
(SHA1): 
```
keytool -list -keystore "C:\Users\CHINU/.android/debug.keystore"
```
(SHA256): +  (SHA1): 
```
keytool -list -v -alias androiddebugkey -keystore "C:\Users\CHINU/.android/debug.keystore"
keytool -list -v -alias androiddebugkey -keystore "C:\Users\SURAVI/.android/debug.keystore"
```
Realease Key
--------------
Right click on android folder Open in terminal 
or 
```
cd android
Run:-gradlew signingReport
```

Generate key to realease apk
-----------------------------
```
keytool -genkey -v -keystore c:\Users\CHINU\key.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias key
```

Extract sha1 key from apk to check
----------------------------------
1st conver .apk or .abb to .zip then extract KEY.RSA or Android.RES from:-\META-INF\

after extracting KEY.RSA or Android.RES wher you have extraxt run cmd in that path and the type:-

keytool -printcert -file KEY.RSA

keytool -printcert -file ANDROIDD.RSA
