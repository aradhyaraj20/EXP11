# Walkthrough - Google Maps Integration

Successfully implemented Google Maps integration in the Android application.

## Changes

### Build & Configuration

#### [build.gradle.kts](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/build.gradle.kts)
- Added `com.google.android.gms:play-services-maps:20.1.0` dependency.
- Updated `compileSdk` and `targetSdk` to 37 to satisfy core library requirements.

#### [AndroidManifest.xml](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/AndroidManifest.xml)
- Added `INTERNET`, `ACCESS_FINE_LOCATION`, and `ACCESS_COARSE_LOCATION` permissions.
- Added `com.google.android.geo.API_KEY` metadata tag for Google Maps API authentication.

### UI & Layout

#### [activity_main.xml](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/res/layout/activity_main.xml)
- Replaced placeholder `TextView` with `FragmentContainerView` hosting `SupportMapFragment`.

### Activity Logic

#### [MainActivity.kt](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/java/com/example/exp11/MainActivity.kt)
- Implemented `OnMapReadyCallback`.
- Configured asynchronous map loading via `getMapAsync(this)`.
- Added a default marker in Sydney with custom zoom level, zoom controls, and compass UI settings.

## Verification Results

### Automated Tests
- Successfully built project with `app:assembleDebug` (`BUILD SUCCESSFUL`).

> [!IMPORTANT]
> **API Key Configuration**: To run the app and display map tiles correctly on your device/emulator, replace `"YOUR_MAPS_API_KEY"` in `AndroidManifest.xml` with your actual Google Maps Android API Key from the Google Cloud Console.
