# Live Location Tracker

A Flutter assignment project using Google Maps and Geolocator.

## Features

- Opens Google Maps and animates the camera to the device's current location.
- Requests a fresh GPS position every 10 seconds while the app is open.
- Moves the current-location marker whenever a new position is received.
- Draws and continuously extends a polyline through recorded positions.
- Shows a marker info window titled **My current location** with latitude and longitude.
- Displays the current coordinates and route-point count on the screen.
- Includes location permission and GPS service checks.

## Requirements

- Flutter 3.38 or newer
- Dart 3.5 or newer
- Android Studio / Xcode
- A Google Cloud project with billing enabled and the Maps SDK for Android enabled. Enable Maps SDK for iOS too when building for iOS.
- A Google Maps API key

## Setup

1. Extract the ZIP and open the `location_tracker` folder in Android Studio or VS Code.
2. Run `flutter create . --platforms=android,ios` from the project folder to generate the native Flutter wrapper files.
3. In Google Cloud Console, create an API key and enable **Maps SDK for Android**. Restrict the key to your Android app package and SHA-1 when publishing. For iOS, enable **Maps SDK for iOS** and use an iOS-restricted key.
4. Replace `YOUR_GOOGLE_MAPS_API_KEY` in `android/app/src/main/AndroidManifest.xml` with your Android key.
5. For iOS, replace `YOUR_GOOGLE_MAPS_API_KEY` in `ios/Runner/AppDelegate.swift` with your iOS key.
6. Run these commands from the project folder:

```bash
flutter pub get
flutter run
```

If the generated platform files replace the supplied manifest or iOS settings, reapply the Google Maps API key, location permissions, and location usage descriptions.

## Run on Android

- Use a physical Android phone or an emulator with Google Play services.
- Turn on device location/GPS.
- Allow location permission when prompted.
- Keep the app open to receive the 10-second updates. This assignment tracks while the app is in the foreground; it does not request background-location permission.

## GitHub

The `.gitignore` excludes generated Flutter build output and local IDE files. Do not commit a production API key to a public repository. Use a restricted key and rotate it if it is exposed.
