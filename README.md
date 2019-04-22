# cordova-build-macos
This is to help overcome some of the problems that you face while you build cordova project on macos


Sometime macos and google drive app wil create those files Icon? and .DS_Store. I believe you can safely delete. However they will be auto generated again. So you have to delete them before every build. 

``rm `find . -name 'Icon?'`; rm `find . -name .DS_Store` ; cordova build --release``


# Generate keytool
#Only the first time
`keytool -genkey -v -keystore foodapp.keystore -alias app_name -keyalg RSA -keysize 2048 -validity 10000`


# Sign the app
`jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.keystore app-release-unsigned.apk app_name`


# Align the app
`~/Library/Android/sdk/build-tools/28.0.2/zipalign  -v 4 apptastic0.6-unsigned.apk apptastic0.6-signed.apk`

# in case you forgot the keystore app name
`keytool -keystore formconnect.keystore -list -v`

# proper integration with AngularJS
``https://medium.com/@EliaPalme/how-to-wrap-an-angular-app-with-apache-cordova-909024a25d79``

# run iOS simulator
1. install Xcode
2. Open emulator
3. build the app after adding platform iOS
4. run the app with the emulator

#install ios sims
``npm install -g ios-sim@next``

#List available simulators
``xcrun simctl list``
#https://www.anexinet.com/blog/install-app-ios-simulator/ 
``xcrun simctl install 34EFC419-1530-4CBD-8564-22DD9C03644A ~/path_to_app/myapp.app``


