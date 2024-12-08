# Authenticator Phone

I use [a dumbphone](https://en.wikipedia.org/wiki/Feature_phone), but I increasingly find myself requiring authenticator and payment apps in everyday life.

This document contains non-generic instructions for turning [a Samsung Galaxy A3 (2017)](https://en.wikipedia.org/wiki/2017_edition_of_the_Samsung_Galaxy_A_series#Galaxy_A3) in to an 'authenticator phone' that only contains one or two essential apps, and no other features. I hope that these instructions can serve as an example that can be generalized to other smartphones. Contributions are welcome.

![Home Screen](home-screen.png)

## Instructions

### Initial set-up

Start off by factory resetting the phone, and then creating and logging in to a new Google account.

### Set a background

After setting up the phone, download [a black background](https://singlecolorimage.com/get/000000/100x100) and set it as the background for both the lock screen and the home screen.

This needs to happen early, since we'll be disabling the _Photos_ app later.

### Set up the initial settings

Connect to all relevant WiFi networks, such as your home network, or a WiFi hot-spot served by your dumbphone.

Next, enable Developer options by following [these](https://developer.android.com/studio/debug/dev-options) instructions, and then go into _System_ > _Developer Options_ and enable _USB Debugging_, so that we can use `adb` to disable apps.

This needs to happen early, since we'll be disabling the _Settings_ app later.

### Install the required apps

Open the Google Play Store and install the apps that you want on the phone. 

This needs to happen early, since we'll be disabling the _Play Store_ app later.

### Installing and configuring a minimal launcher

Install [Before Launcher](https://play.google.com/store/apps/details?id=com.beforesoft.launcher), open the settings, and configure it as follows:

1. Go into _Styles & Themes_ > _Backgrounds & Themes_ and switch to a theme with a black background, in order to match the lock screen.
2. Go into _Apps_ and set "_App List Screen_" to _Off_.
3. Go into Notification Filter and set "_Notification Filter Screen_" to _Off_.

Next, add your required apps to the home screen.

### Disabling all other apps

Connect the phone to a computer, and use `adb` to disable all visible apps:

```bash
adb shell pm disable-user --user 0 com.android.chrome
adb shell pm disable-user --user 0 com.facebook.katana
adb shell pm disable-user --user 0 com.google.android.youtube
adb shell pm disable-user --user 0 com.google.android.music
adb shell pm disable-user --user 0 com.google.android.apps.maps
adb shell pm disable-user --user 0 com.google.android.videos
adb shell pm disable-user --user 0 com.samsung.android.calendar
adb shell pm disable-user --user 0 com.microsoft.office.excel
adb shell pm disable-user --user 0 com.microsoft.office.word
adb shell pm disable-user --user 0 com.microsoft.office.powerpoint
adb shell pm disable-user --user 0 com.samsung.android.app.notes
adb shell pm disable-user --user 0 com.samsung.android.contacts
adb shell pm disable-user --user 0 com.sec.android.app.camera
adb shell pm disable-user --user 0 com.sec.android.app.popupcalculator
adb shell pm disable-user --user 0 com.linkedin.android
adb shell pm disable-user --user 0 com.sec.android.app.shealth
adb shell pm disable-user --user 0 com.sec.android.app.myfiles
adb shell pm disable-user --user 0 com.samsung.knox.securefolder
adb shell pm disable-user --user 0 com.google.android.apps.maps
adb shell pm disable-user --user 0 com.android.documentsui
adb shell pm disable-user --user 0 com.google.android.apps.photos
adb shell pm disable-user --user 0 com.samsung.intrafficreply
adb shell pm disable-user --user 0 com.google.android.gm
adb shell pm disable-user --user 0 com.samsung.voiceserviceplatform
adb shell pm disable-user --user 0 com.sec.android.app.voicenote
adb shell pm disable-user --user 0 com.sec.android.gallery3d
adb shell pm disable-user --user 0 com.samsung.android.svoice
adb shell pm disable-user --user 0 com.sec.android.app.samsungapps
adb shell pm disable-user --user 0 com.samsung.android.oneconnect
adb shell pm disable-user --user 0 com.sec.android.app.fm
adb shell pm disable-user --user 0 com.google.android.talk
adb shell pm disable-user --user 0 com.microsoft.skydrive
adb shell pm disable-user --user 0 com.samsung.android.email.provider
adb shell pm disable-user --user 0 com.sec.android.app.clockpackage
adb shell pm disable-user --user 0 com.samsung.android.voc
adb shell pm disable-user --user 0 com.google.android.googlequicksearchbox
adb shell pm disable-user --user 0 com.sec.android.messaging
adb shell pm disable-user --user 0 com.samsung.android.messaging
adb shell pm disable-user --user 0 com.google.android.apps.docs
adb shell pm disable-user --user 0 com.sec.android.app.launcher
adb shell pm disable-user --user 0 com.facebook.appmanager
adb shell pm disable-user --user 0 com.facebook.services
adb shell pm disable-user --user 0 com.facebook.system
adb shell pm disable-user --user 0 com.android.vending
adb shell pm disable-user --user 0 com.android.settings
```

This is the list of apps that I've experimentally found can be safely disabled _without_ stopping the phone from booting. It completely empties the apps list, beyond the essential apps that you've installed yourself.

## Maintenance

If you need to update apps or connect to additional Wi-Fi networks, you might need to temporarily re-enable the Play Store and the Settings app:

```bash
adb shell pm enable com.android.vending
adb shell pm enable com.android.settings
```

Afterwards, you can disable them again by running the following commands:

```bash
adb shell pm disable-user --user 0 com.android.vending
adb shell pm disable-user --user 0 com.android.settings
```
