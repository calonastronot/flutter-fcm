flutter create flutter_fcm
cd flutter_fcm
=======================
lalu install firebase messaging

firebase_messaging: ^7.0.3
https://pub.dev/packages/firebase_messaging/versions

tambahkan code di file android/app/src/build.gradle
=============================================================
apply plugin: 'com.google.gms.google-services'

tambahkan code di file android/app/build.gradle
=============================================================
classpath 'com.google.gms:google-services:4.2.0'


tambahkan code di file android/app/src/main/AndroidManifest.xml
==============================================================
<intent-filter>
 <action android:name="FLUTTER_NOTIFICATION_CLICK"/>
 <category android:name="android.intent.category.DEFAULT"/>
</intent-filter>
==============================================================
Download google-service.json dari  **firebase**, simpan di folder android/app/ 

di main dart tambahkan 
import 'package:firebase_messaging/firebase_messaging.dart';

String _message = '';

 final FirebaseMessaging _firebaseMessaging = FirebaseMessaging();
 _firebaseMessaging.getToken().then((token) => print(token));
