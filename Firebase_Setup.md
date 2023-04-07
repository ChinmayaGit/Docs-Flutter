app/build.gradle
```

    defaultConfig {
    
    
        multiDexEnabled true
    }
apply plugin: 'com.google.gms.google-services'

dependencies {
    implementation 'com.android.support:multidex:1.0.3'
    implementation platform('com.google.firebase:firebase-bom:30.2.0')
    implementation 'com.google.firebase:firebase-analytics'
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
    implementation 'com.google.android.gms:play-services-location:19.0.1'
}
```
build.gradle

```
    dependencies {
        classpath 'com.android.tools.build:gradle:7.1.2'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
        classpath 'com.google.gms:google-services:4.3.13'
    }

```
