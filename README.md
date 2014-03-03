SteedOS Apps PhoneGap Shell
===========

SteedOS Apps for Business is a cloud-based productivity suite that helps you and your team connect and get work done from anywhere on any device.   It's simple to setup, use and manage, allowing you to work smarter and focus on what really matters.

This project is initialized from PhoneGap 3.3.0 with following commands:

export PATH=${PATH}:~/svn/sdk/platform-tools:~/svn/sdk/tools

source ~/.bash_profile

sudo npm install -g cordova

cordova create creator-phonegap com.steedos.creator Creator

cd creator-phonegap

cordova plugin add org.apache.cordova.inappbrowser

cordova plugin add org.apache.cordova.dialogs

cordova plugin add org.apache.cordova.vibration

cordova plugin add https://github.com/phonegap-build/PushPlugin.git

cordova plugin add org.apache.cordova.statusbar

cordova plugin add https://github.com/VitaliiBlagodir/cordova-plugin-datepicker

cordova plugin add org.apache.cordova.contacts

cordova plugin add org.apache.cordova.splashscreen

=============

Install Ant ...

brew update

brew install ant

=============

To build Android: 

export PATH=${PATH}:~/svn/sdk/platform-tools:~/svn/sdk/tools

mkdir platforms

cordova platform remove android

cordova platform add android

cordova build android --release

# Sign
jarsigner -verbose -keystore ../steedos-certs/android/android.keystore -signedjar dist/SteedOS_Creator_signed.apk platforms/android/bin/Creator-release-unsigned.apk android

# Optimize
rm dist/SteedOS_Creator_1.0.0.apk
zipalign -v 4 dist/SteedOS_Creator_signed.apk dist/Creator_1.0.0.apk

=============

To build iOS: 

cordova platform remove ios

cordova platform add ios

cordova build ios --release
