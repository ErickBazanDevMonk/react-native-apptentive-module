# react-native-apptentive-module
ReactNative module for [Apptentive](https://github.com/apptentive/apptentive-ios) 5.0.+
Version 1.2.1

## Installation

```bash
npm install --save react-native-apptentive-module
```
```bash
react-native link react-native-apptentive-module
```

### iOS
iOS is depending on CocoaPods. Follow the Apptentive guides to learn how to add apptentive.
Pay extra attention if you can't or don't want to use `use_frameworks!`
https://learn.apptentive.com/knowledge-base/ios-integration-reference/#cocoapods

### Android
Android needs some extra attention as well, because Apptentive needs a reference to your 
Application. In your Application class, make sure the package is added as followed:
```java
new RNApptentivePackage(this)
``` 

## Usage
Everything is handled in JS, no native code necessary, other than described above. 
```js
// Import
import Apptentive from 'react-native-apptentive-module';
```

The following calls are implemented:
```js
/**
 * Configure Apptentive using your key and signature.
 * You can add an optional AppleID to redirect the user to the App Store
 * @param appKey Found in Apptentive Dashboard
 * @param appSignature Found in Apptentive Dashboard
 * @param appleID optional Found in iTunesConnect
 * @return Promise
 */
Apptentive.register(appKey, appSignature, appleID);

/**
 * Present the feedback view
 * @return Promise with success boolean or error
 */
Apptentive.presentMessageCenter();

/**
 * Present the feedback view with custom data
 * @param customData optional Object
 * @return Promise with success boolean or error
 */
Apptentive.presentMessageCenterWithCustomData(customData);

/**
 * Log an event to apptentive
 * @param event String event name
 * @return Promise with success boolean or error
 */
Apptentive.engageEvent(event);

/**
 * Send person data to apptentive
 * @param key Data key
 * @param value Value
 * @return Promise returning true or error
 */
Apptentive.addPersonData("key1", "string");
Apptentive.addPersonData("key2", 123);
Apptentive.addPersonData("key3", true);

/**
 * Send person data to apptentive
 * @param key Data key
 * @param value String value
 * @return Promise returning true or error
 */
Apptentive.addPersonDataString(value, key);

/**
 * Send person data to apptentive
 * @param key Data key
 * @param value Number value
 * @return Promise returning true or error
 */
Apptentive.addPersonDataNumber(value, key);

/**
 * Send person data to apptentive
 * @param key Data key
 * @param value Bool value
 * @return Promise returning true or error
 */
Apptentive.addPersonDataBool(value, key);

/**
 * Send device data to apptentive
 * @param key Data key
 * @param value Value
 * @return Promise returning true or error
 */
Apptentive.addDeviceData("key1", "string");
Apptentive.addDeviceData("key2", 123);
Apptentive.addDeviceData("key3", true);

/**
 * Send device data to apptentive
 * @param key Data key
 * @param value String value
 * @return Promise returning true or error
 */
Apptentive.addDeviceDataString(value, key);

/**
 * Send device data to apptentive
 * @param key Data key
 * @param value Number value
 * @return Promise returning true or error
 */
Apptentive.addDeviceDataNumber(value, key);

/**
 * Send device data to apptentive
 * @param key Data key
 * @param value Bool value
 * @return Promise returning true or error
 */
Apptentive.addDeviceDataBool(value, key);
```
