# Boot Launcher (modified to run as service)

Launch your Apache Cordova Android app automatically when the device is booted without showing it on foreground. It's like a service running Javascript.

You will be able to use plugins like [background-app](https://github.com/MobileChromeApps/cordova-plugin-background-app/) and [local-notifications](https://github.com/katzer/cordova-plugin-local-notifications), as well as AJAX calls.

Please note that, depending on what you want to do, your app will slow down the user's device. Also, Android may kill your app as it needs RAM (it's recommended not to disable the ongoing notification that comes with background-app plugin). Don't do what you don't need to do.

## Install

1. Fork this repository

2. In `src/android/BootLauncher.java` line 13, replace `uk.co.ilee.CordovaApp.class` with your main activity class name. For informations about how to get it, read [here](https://github.com/jesobreira/cordova-plugin-boot-launcher/tree/patch-1#notes-about-main-activity-class-name).

3. Add your forked plugin via the CLI:

```
cordova plugin add https://github.com/[YOUR_USERNAME]/cordova-plugin-boot-launcher.git
```

4. Once you've done it, your app will already run at startup, but you will not see anything because it will run as service. Use the plugins mentioned above (mainly background-app) to do any action.

## Platforms

Android only.

## License

[MIT License](http://ilee.mit-license.org)
