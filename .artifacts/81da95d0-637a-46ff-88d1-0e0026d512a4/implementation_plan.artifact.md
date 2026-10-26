# Google Maps Integration Implementation Plan

Develop an Android application that integrates Google Maps to display an interactive map with markers, zoom controls, and location features.

## User Review Required

> [!IMPORTANT]
> **Google Maps API Key Required**: To view Google Maps, you must provide a valid Google Maps Android API Key. This plan includes instructions on adding your API key to `local.properties` and configuring it in `AndroidManifest.xml`.

## Open Questions

- None at this time. Standard Google Maps Fragment approach with `OnMapReadyCallback` will be used.

## Proposed Changes

### Build Configuration

#### [MODIFY] [build.gradle.kts](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/build.gradle.kts)
- Add Google Play Services Maps dependency (`com.google.android.gms:play-services-maps`).

### Manifest & Configuration

#### [MODIFY] [AndroidManifest.xml](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/AndroidManifest.xml)
- Add INTERNET permission and ACCESS_FINE_LOCATION / ACCESS_COARSE_LOCATION permissions (optional for My Location layer).
- Add `com.google.android.geo.API_KEY` metadata tag pointing to the API key placeholder.

### Layout

#### [MODIFY] [activity_main.xml](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/res/layout/activity_main.xml)
- Replace `TextView` with a `FragmentContainerView` hosting `SupportMapFragment` or a custom layout containing map controls.

### MainActivity & Logic

#### [MODIFY] [MainActivity.kt](file:///C:/Users/aradh/AndroidStudioProjects/EXP11/app/src/main/java/com/example/exp11/MainActivity.kt)
- Implement `OnMapReadyCallback`.
- Initialize the map fragment asynchronously.
- Add a custom marker (e.g., Sydney or a custom location) and zoom/pan to it.
- Add runtime permission handling for location services if enabling "My Location".

## Verification Plan

### Automated Tests
- Build verification using `./gradlew assembleDebug` to ensure compilation and dependency resolution succeed.

### Manual Verification
- Deploy the app to an emulator or physical device.
- Verify that Google Maps renders correctly (requires valid API key).
- Test panning, zooming, and marker interactions.
