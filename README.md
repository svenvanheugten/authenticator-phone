Phone: Samsung Galaxy A3 (2017)
Launcher: OLauncher

Disable pretty much all apps:

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
adb shell pm disable-user --user 0 com.android.settings
adb shell pm disable-user --user 0 com.google.android.apps.docs
adb shell pm disable-user --user 0 com.sec.android.app.launcher
adb shell pm disable-user --user 0 com.android.vending
adb shell pm disable-user --user 0 com.facebook.appmanager
adb shell pm disable-user --user 0 com.facebook.services
adb shell pm disable-user --user 0 com.facebook.system
```

Re-enable the Play Store temporarily to allow updating apps:

```bash
adb shell pm enable com.android.vending
```

Disable it again:

```bash
adb shell pm disable-user --user 0 com.android.vending
```
