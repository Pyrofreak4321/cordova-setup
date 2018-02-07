# Cordova Setup Guide

### CMDS
+ `cordova create <path> <id> <name>`

+ `cordova platform add <android,ios>`

+ `cordova build <android,ios>`

+ `cordova run <android,ios>`

+ `cordova-icon`

+ `cordova-spash`

+ `cordova build android --release -- --keystore=../<keystoreName>.keystore --alias=XXXX`

+ `keytool -genkey -v -keystore ../<keystoreName>.keystore -alias <Keystore AliasName> -keyalg rsa -keysize 2048 -validity 10000`

### basic plugins
```
cordova plugin add cordova-plugin-device
cordova plugin add cordova-plugin-splashscreen
cordova plugin add cordova-plugin-statusbar
cordova plugin add cordova-plugin-dialogs
cordova plugin add cordova-plugin-app-preferences
```
### initialization

+ add to config.xml
```
  <platform name="android">
    ...
    <hook type="before_build" src="hooks/fixSoftInput.js" />
    <hook type="before_run" src="hooks/fixSoftInput.js" />
    <preference name="StatusBarBackgroundColor" value="#000000" />
    ...
  </platform>
  <platform name="ios">
    ...
    <preference name="StatusBarBackgroundColor" value="#ffffff" />
    ...
  </platform>

  <preference name="Orientation" value="all" />
  <preference name="StatusBarOverlaysWebView" value="false" />
  <preference name="SplashScreenDelay" value="5000" />
  <preference name="FadeSplashScreenDuration" value="1000"/>
  <preference name="SplashMaintainAspectRatio" value="true" />
  <preference name="ShowSplashScreenSpinner" value="false"/>
```
+ copy `fixSoftInput.js` to `<root>\hooks\`
+ replace contents of `<root>\www\js\` with contents of `cordova-setup\js`
+ update app title in `index.js`
+ replace contents of `<root>\www\css\` with contents of `cordova-setup\css`
+ replace `<root>\www\index.html` with `cordova-setup\index.html`
+ update app title in `index.html`
