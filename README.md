# Boot Launcher (run as service fork)

Launch your Apache Cordova Android app automatically when the device is booted without showing it on foreground. It's like a service running Javascript.

You will be able to use plugins like [background-app](https://github.com/MobileChromeApps/cordova-plugin-background-app/) and [local-notifications](https://github.com/katzer/cordova-plugin-local-notifications), as well as AJAX calls.

Please note that, depending on what you want to do, your app will slow down the user's device. Also, Android may kill your app as it needs RAM (it's recommended not to disable the ongoing notification that comes with background-app plugin). Don't do what you don't need to do.

## Install

1. Fork this repository

2. In `src/android/BootLauncher.java` line 13, replace `com.yourapp.CordovaApp.class` with your main activity class name. For informations about how to get it, read [here](https://github.com/jesobreira/cordova-plugin-boot-launcher/tree/patch-1#notes-about-main-activity-class-name).

3. Add your forked plugin via the CLI:

```
cordova plugin add https://github.com/[YOUR_USERNAME]/cordova-plugin-boot-launcher
```

4. Once you've done it, your app will already run at startup, but you will not see anything because it will run as service. Use the plugins mentioned above (mainly background-app) to do any action.

## Notes about main activity class name

Cordova/Phonegap seems to act differently based on the environment when generating the value you must set on the step 2. For example, if you are using Phonegap Build, it's useful if the class name is `[ your app id].[your app name].class`. For example, if your app id is "com.example.app" and your app name is "My Cool App", then the class name will be "com.example.app.MyCoolApp.class" (note that the spaces are removed). However, if you are using Cordova from CLI, it's supposed to use the format `[your app id].MainActivity.class` (on the example above, it would be com.example.app.MainActivity.class).

Anyway, it's easy to get the class name by reading the AndroidManifest.xml. You will find your app id on the tag `<manifest>`, attribute `package`, and the activity name on the tag `<activity>`, attribute `android:name`.

![Where to find](http://i.stack.imgur.com/62gX6.png)

## Platforms

Android only.

## License

[MIT License](http://ilee.mit-license.org)
