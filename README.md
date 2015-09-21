# RealtimeMessaging-ReactNativeAndroidExample
Realtime Cloud Messaging React Native for Android Example (including GCM mobile push notifications)

This example is a simple app that allows you to send and receive messages between devices using React Native and the Realtime Messaging React Native SDK.
 
[Realtime Cloud Messaging](http://framework.realtime.co/messaging) is a highly-scalable pub/sub message broker, allowing you to broadcast messages to millions of users, reliably and securely. It's all in the cloud so you don't need to manage servers.

[React Native](http://facebook.github.io/react-native/) enables you to build world-class application experiences on native platforms using a consistent developer experience based on JavaScript and React.


##How to test this demo application

*	Create a new react-native project using the following command `react-native init RealtimeRCT`

*	Replace index.android.js for the one provided in this repository.

* Create a new react-native project. [Check react-native getting started](http://facebook.github.io/react-native/docs/getting-started.html#content)

* On the terminal, go to `PROJECT_DIR/node_modules/react-native`.

* Execute

		 npm install --save react-native-realtimemessaging-android

* Drag all files `node_modules/react-native-realtimemessaging-android` to your `src` package folder.

* Add compile `co.realtime:messaging-android:2.1.+` to app dependencies in your `build.gradle` file.

* Drag `RCTRealtimeMessagingAndroid.js` to the root of your project.

* Add `.addPackage(new CustomReactPackage())` to the `onCreate` method of `MainActivity`.

* **If you want to use push notifications**, set `MainActivity` extending `RealtimePushNotificationActivity`.

	* Edit AndroidManifest.xml
			
			...
			<permission android:name="[YOUR RECEIVER PACKAGE].permission.C2D_MESSAGE" android:protectionLevel="signature" />
			
		    <uses-permission android:name="[YOUR RECEIVER PACKAGE].permission.C2D_MESSAGE" />
		    
		    <uses-permission android:name="com.google.android.c2dm.permission.RECEIVE" />
		    ...
		    
		    <application
		    ...
		    <meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
	        <receiver
	            android:name=".GcmReceiver"
	            android:permission="com.google.android.c2dm.permission.SEND" >
	            <intent-filter>
	                <action android:name="com.google.android.c2dm.intent.RECEIVE" />
	                <category android:name="[YOUR RECEIVER PACKAGE]" />
	            </intent-filter>
	        </receiver>
			    ...
		    <application/>




 You are ready to go.

##Testing the custom push notifications delivery

To test the Realtime Custom Push Notifications you need to use the Realtime Mobile Push REST API to send a custom push with the following POST to `https://ortc-mobilepush.realtime.co/mp/publish`

	{
	   "applicationKey": "[INSERT YOUR APP KEY]",
	   "privateKey": "[INSERT YOUR APP PRIVATE KEY]",
	   "channel" : "[INSERT CHANNEL TO SEND PUSH]",
	   "message" : "[INSERT ALERT TEXT]",
	    "payload" : "{
	     \"sound\" : \"default\",
	     \"badge\" : \"1\",
	     \"name\" : \"Joe\",
	     \"age\" : \"48\"
	    }"
	}

Have fun pushing!

	
## Authors
Realtime.co
	

