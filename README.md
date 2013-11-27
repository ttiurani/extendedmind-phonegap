Extended Mind - Phonegap
========================

Github destroys MD line wrapping - read this locally!

Extended Mind - PhoneGap builds

Setup PhoneGap build
--------------------

  Copy sample conf:
    > cp /usr/share/maven/conf/settings.xml ~/.m2/

  Open it and under <servers>, add the following:
      <servers>
          <server>
        <id>phonegap-build</id>
        <username>YOUR_ADOBE_EMAIL</username>
        <password>YOUR_ADOBE_PWD</password>
      </server>
      <server>
        <id>ios-developer-certificate</id>
        <privateKey>${user.home}/.phonegap/ios/[YOUR P12 FILE]</privateKey>
        <passphrase>[YOUR P12 PASSWORD]</passphrase>
      </server>
      <server>
        <id>android-developer-certificate</id>
        <privateKey>${user.home}/.phonegap/android/[YOUR ANDROID KEYSTORE]</privateKey>
        <passphrase>[YOUR KEYSTORE PASSWORD]</passphrase>
        <username>[YOUR KEYSTORE ALIAS]</username>
        <password>[YOUR KEYSTORE PASSWORD]</password>
      </server>

   > cp [YOUR ANDROID KEYSTORE FILE] ~/.phonegap/android/
   > cp [IOS DISTRIBUTION CERT] ~/.phonegap/ios/
   > cp [IOS TESTFLIGHT DISTRIBUTION PROFILE] ~/.phonegap/ios/

Android
-------

Download android-sdk
Add android-sdk-linux/tools and /platform-tools to PATH (Platform tools does not exist at this point but add it anyway).
Install ADT Tools to Eclipse

To get adb to run, it might be necessary in Arch linux to enable [multilib] in /etc/pacman.conf and run:
sudo pacman -S lib32-glibc lib32-zlib lib32-libstdc++5 lib32-ncurses lib32-gcc-libs

Open in Eclipse Window->Customize Perspective.. and enable Android links.
Open Window->Android SDK Manager and install API 18, API 17 and Tools.
NOTE: You need to try to install them multiple times, as everything won't be installed with one click!

* Phonegap

sudo pacman -S npm
sudo npm install -g cordova
sudo npm install -g phonegap
Open this folder and run:
cordova add platform linux

* Import project

Window->Android Virtual Device Manager
Add Nexus 4 as "nexus4_17" using 4.2.2 and ARM.

In Eclipse Import.. Existing Android ..
Run Debug as.. Android Application
Open Logcat from Window->Show View->Android->Logcat

iOS
---

Install NodeJS with "brew install nodejs".
Install Cordova with "sudo npm install -g cordova".
Install Phonegap with "sudo npm install -g phonegap".
Open this folder and run "mkdir platforms" followed by "cordova platform add ios".
