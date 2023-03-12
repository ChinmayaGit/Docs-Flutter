### Hosting
```
firebase init hosting
```


### New Algolia Setup
```
npm install algoliasearch --save
```


### NPM Install
```
npm install -g firebase-tools
```


### NPM Uninstall
```
npm uninstall -g firebase-tools

and clean this folder (C:\Users\CHINU\.config\configstore)
```


### Firebase Use
```
cd project_name

firebase use projectname

ex:-firebase use cargo-d634e

firebase use --clear
```


### NEW Setup
```
npm install -g firebase-tools
     
(if login;- firebase logout)

firebase login or firebase logout(to change gmail account)

firebase init functions (make sure function/packge.jeso must be 8 "node":8)

firebase use --add

firebase deploy --only functions

firebase deploy --only functions:function1,functions:function2
```

### Existing Setup
```
npm install -g firebase-tools

[if login;]- firebase logout

firebase login (or firebase logout(to change gmail account))

firebase use --add

firebase init functions

firebase deploy --only functions
```

### Firebase Clean
```
delet these files from project folder 
(D:\Softwares\Android Studio\Flutter\Projects\jhoom)

.firebaserc
firebase.json

firebase
firebase-debug.log
```

### To update to new version
```
npm install -g npm@9.2.0
```


### Live DEMO
```
npm install -g firebase-tools

firebase login (or firebase logout(to change gmail account))


You're about to initialize a Firebase project in this directory:

  D:\Softwares\Android Studio\Flutter\Projects\fluttershare

? Are you ready to proceed? Yes

=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add,
but for now we'll just set up a default project.

? Please select an option: Don't set up a default project

=== Functions Setup

A functions directory will be created in your project with a Node.js
package pre-configured. Functions can be deployed with firebase deploy.

? What language would you like to use to write Cloud Functions? JavaScript
? Do you want to use ESLint to catch probable bugs and enforce style? No
+  Wrote functions/package.json
+  Wrote functions/index.js
+  Wrote functions/.gitignore
? Do you want to install dependencies with npm now? Yes

> protobufjs@6.9.0 postinstall D:\Softwares\Android Studio\Flutter\Projects\fluttershare\functions

> protobufjs@6.9.0
postinstall D:\Softwares\Android Studio\Flutter\Projects\fluttershare\functions\node_modules\proto


D:\Softwares\Android Studio\Flutter\Projects\fluttershare>firebase use --add
? Which project do you want to add? fluttershare-29dc5
? What alias do you want to use for this project? (e.g. staging) firebase use ----(Type=firebase use)

Created alias firebase use for fluttershare-29dc5.
Now using alias firebase use (fluttershare-29dc5)

D:\Softwares\Android Studio\Flutter\Projects\fluttershare>firebase deploy --only functions

=== Deploying to 'fluttershare-29dc5'...

i  deploying functions
i  functions: ensuring required API cloudfunctions.googleapis.com is enabled...
+  functions: required API cloudfunctions.googleapis.com is enabled
i  functions: preparing functions directory for uploading...
i  functions: packaged functions (27.8 KB) for uploading
+  functions: functions folder uploaded successfully
i  functions: creating Node.js 8 function onCreateFollower(us-central1)...
+  functions[onCreateFollower(us-central1)]: Successful create operation.

+  Deploy complete!

Project Console: https://console.firebase.google.com/project/fluttershare-29dc5/overview
```
