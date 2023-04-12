# Teamgram Android Client

## Step by Step instructions to build android client

### Prerequisites

- Java JDK from here according to your mac specifications from [here](https://www.oracle.com/pk/java/technologies/downloads/#jdk20-mac)
- Download and set up Android Studio from [here](https://developer.android.com/studio) according to your mac specifications.
- Setup Git VCS from [here](https://git-scm.com/download/mac) for macOS

## Teamgram Android Client Test to make sure build works

- Navigate to where you want to setup your project then run
  `git clone https://github.com/teamgram/teamgram-android.git`
- Then open the cloned repository in Android Studio (don't import only **open**)
- Go to Tools > SDK Manager > Android SDK > SDK Tools > Select NDK (Side by side) and press Ok to install Andoid NDK
- Once the NDK is installed wait for Gradle to finish updating the indexes (It may take a while).
- You are now ready to compile Telegram. Go to the "Build" menu in Android Studio and click on "Make Project" to build the app.
- Once the build is successful, you can run the Telegram app on an emulator or a physical Android device for testing or distribution. To run the app on an emulator, go to the "Run" menu in Android Studio and click on "Run 'app'" to select an emulator or create a new one.
- To create an .apk/.abb file go to Build > Build Bundle(s)/APK(s) the generated APK will be under `TMessagesProj_App/build/outputs/apk/afat/debug`

## Teamgram android client setup with firebase, private keystore and API keys.

- Navigate to where you want to setup your project then run
  `git clone https://github.com/teamgram/teamgram-android.git`
- Copy your release.keystore file into the TMessagesProj/config directory of the cloned repository.
- Open the gradle.properties file in the root directory of the repository and fill out the following variables with the appropriate values from your release.keystore:

```
RELEASE_KEY_PASSWORD=<your_release_key_password>
RELEASE_KEY_ALIAS=<your_release_key_alias>
RELEASE_STORE_PASSWORD=<your_release_store_password>
```

- Go to https://console.firebase.google.com/ and create two Android apps with application IDs org.telegram.messenger and org.telegram.messenger.beta. Turn on Firebase Messaging for both apps and download the google-services.json file for each app. Copy the google-services.json files to the same folder as TMessagesProj in the cloned repository.
- Fill out the values in `TMessagesProj/src/main/java/org/telegram/messenger/BuildVars.java` file with the appropriate data. You can find links and instructions for obtaining the required data in the comments in the BuildVars.java file.
- Then open the cloned repository in Android Studio (don't import only **open**)
- Go to Tools > SDK Manager > Android SDK > SDK Tools > Select NDK (Side by side) and press Ok to install Andoid NDK
- Once the NDK is installed wait for Gradle to finish updating the indexes (It may take a while).
- You are now ready to compile Telegram. Go to the "Build" menu in Android Studio and click on "Make Project" to build the app.
- Once the build is successful, you can run the Telegram app on an emulator or a physical Android device for testing or distribution. To run the app on an emulator, go to the "Run" menu in Android Studio and click on "Run 'app'" to select an emulator or create a new one.
- To create an .apk/.abb file go to Build > Build Bundle(s)/APK(s) the generated APK will be under `TMessagesProj_App/build/outputs/apk/afat/debug`
- If you want to generate a signed APK for distribution, go to the "Build" menu in Android Studio and click on "Generate Signed Bundle/APK". Follow the prompts to create a signed APK according to your desired configuration.
- The generated APK can be found in the `teamgram-android/app/build/outputs/apk/ directory`.
