# SOAP LAB Android project (v0.4)

This is an Android Studio project wrapping the existing SOAP LAB web interface in an Android WebView. It provides an app icon/launcher entry, local HTML assets, JavaScript, and on-device localStorage for saved recipes and settings.

## Build an APK
1. Open this folder as a project in Android Studio.
2. Allow Gradle sync and install Android SDK Platform 35 / Build Tools when prompted.
3. Choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. For a test install, use the generated `app-debug.apk` from `app/build/outputs/apk/debug/`.

The project uses Android Gradle Plugin 8.7.3 and Java. Internet permission is only used for online equipment image/source links; core app pages and embedded starter database are packaged locally.

## Important notes
- This is the Android source project, not a prebuilt APK. This environment does not have the Android SDK/build tools needed to compile and sign an APK here.
- Some Chrome/PWA-only features such as service-worker installation are not needed in the Android wrapper; app content is loaded from packaged assets.
- User records are stored in WebView local storage on this device. Uninstalling or clearing app storage may delete those records; export backups when available.
- Ingredient and SAP data are educational estimates. This app does not provide production-ready lye calculations or validate a real soap formula. Use verified supplier data and trained adult supervision for hazardous soapmaking operations.

## Build APK in the cloud (phone-friendly route)
This project includes `.github/workflows/build-apk.yml` for building a debug APK with GitHub Actions.
Upload the project folder to a GitHub repository, open the repository's **Actions** tab, run **Build SOAP LAB APK**,
and download the `soap-lab-debug-apk` artifact from the completed workflow. Extract the artifact ZIP to get
`app-debug.apk`, then open it on your Android phone to install. Android may ask you to allow installs from the
browser/files app. Only install APKs you built or trust. This debug APK is for testing, not Play Store release.
