# Realtime Messaging example using React Native for Android (including Push Notifications)
Realtime Cloud Messaging React Native for Android Example (including GCM mobile push notifications)

This example is a simple app that allows you to send and receive messages between devices using React Native and the Realtime Messaging React Native SDK for Android.
 
[Realtime Cloud Messaging](http://framework.realtime.co/messaging) is a highly-scalable pub/sub message broker, allowing you to broadcast messages to millions of users, reliably and securely. It's all in the cloud so you don't need to manage servers.

[React Native](http://facebook.github.io/react-native/) enables you to build world-class application experiences on native platforms using a consistent developer experience based on JavaScript and React.


##How to test this demo application

*	Create a new react-native project with name `RealtimeRCT`. [Check react-native getting started](http://facebook.github.io/react-native/docs/getting-started.html#content)

*	Replace index.android.js for the one provided in this repository.

*	Install the RCTRealtimeMessagingAndroid SDK, follow the [documentation](https://github.com/realtime-framework/RCTRealtimeMessagingAndroid) on realtime framework GitHub.

*	Create a Google project in [here](https://code.Google.com/apis/).

*	Create a Realtime messaging account and configure the Google Api key on the account, you can check more details of this process in the android native configuration guide for [push notification](http://messaging-public.realtime.co/documentation/starting-guide/mobilePushGCM.html). 
**Note: Theres no need to change Manifest.xml in react-native, that is just for android native.**	

*	Update index.android.js to use your Google project number and Realtime application key.

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
	

