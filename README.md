# Digital Theodolite (Android prototype)

A Kotlin/Android Studio prototype for the Redmi Note 13 Pro+ 5G.

## What it does
- Opens the rear camera preview with a center crosshair.
- Reads Android's rotation-vector sensor.
- Estimates the rear-camera optical axis as device -Z.
- Displays azimuth corrected from magnetic north to true north using Android's GeomagneticField when location is available.
- Displays altitude and DMS with six decimal places of arcseconds, plus ten decimal places of degrees.

## Important limitations
This is a prototype, not a certified surveying instrument. Extra displayed digits are formatting precision, not measurement accuracy. Phone magnetometers are affected by magnetic materials, cases, speakers, vehicles, wiring, and calibration. The sensor orientation model assumes the camera optical axis is aligned with the phone's rear normal; real camera module alignment and preview cropping/stabilization can introduce offsets. True-north correction depends on a reasonably fresh location and the geomagnetic model. GPS does not determine the pointing direction.

For serious measurements, calibrate against a known reference and compare repeated readings. Do not interpret six decimal places of arcseconds as actual arcsecond accuracy.

## Build an APK
1. Install Android Studio on a computer.
2. Open this folder (`DigitalTheodolite`) as an existing project.
3. Allow Gradle sync and install the Android SDK Platform 35 if prompted.
4. Connect the Redmi Note 13 Pro+ with USB debugging enabled, or use Build > Build Bundle(s) / APK(s) > Build APK(s).
5. The debug APK is normally generated at `app/build/outputs/apk/debug/app-debug.apk`.

## Current prototype scope
This initial build uses TYPE_ROTATION_VECTOR. It does not yet implement a survey-grade optical collimation calibration, manual declination override, averaging/locking, CSV export, or a tripod leveling workflow. Those are sensible next development steps.
