


# Getting Started: Developers


<a name="wepsim-apache-cordova"/>

# WepSIM for Apache Cordova

## 1) Prepare the Apache Cordova Project:

+ 1.1) Follow Apache Cordova tutorial in order to create a new project:
  ```bash
  npm install -g cordova
  cordova create wepsim es.uc3m.inf.arcos.wepsim WepSIM
  cd wepsim
  cordova platform add android
  cordova platform add ios
  ```

+ 1.2) Install at least the following plugins:
  ```bash
  cordova plugin add cordova-plugin-console
  cordova plugin add cordova-plugin-device
  cordova plugin add cordova-plugin-dialogs
  cordova plugin add https://github.com/apache/cordova-plugin-file-transfer.git
  cordova plugin add cordova-plugin-file
  cordova plugin add cordova-plugin-splashscreen
  cordova plugin add cordova-plugin-web-share
  ```

## 2) Update WepSIM files:

+ 2.1) Copy WepSIM files into the www directory:
  ```bash
  wget https://github.com/wepsim/wepsim/archive/refs/heads/master.zip
  unzip master.zip
  ```

+ 2.2) Build www for the Apache Cordova project:
  ```bash
  ./wepsim-master/devel/mk_cordova.sh
  ```

## 3) Build Android .apk:

+ 3.1) Build .apk:
  ```bash
  cordova build android --debug
  ```

+ 3.2) Run WepSIM's App...
  + ... on Emulator:
    ```bash
    cordova run android
    ```
  + ... on Device:
    ```bash
    adb -d install -r ./platforms/android/app/build/outputs/apk/debug/app-debug.apk
    ```

