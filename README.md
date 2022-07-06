# issue 3861
### GitHub link
- https://github.com/firebase/firebase-android-sdk/issues/3861
### Prerequisite
- Add google-services.json
### Steps to reproduce
- Open app
- Sync gradle builds
### Summary
- Created a clean app and added a dynamic-feature module named `:feature1`, added Firebase Crashlytics NDK in `build.gradle` of `:feature1`
### Error
- Syncing gradle causes error: `Caused by: groovy.lang.MissingMethodException: No signature of method: build_` is encountered when `firebaseCrashlytics` is included in the `dynamic-feature` module.
- Relevant code:
```
buildTypes {
  debug {
      firebaseCrashlytics {   // If I comment this block, no gradle sync error
          nativeSymbolUploadEnabled false
      }
  }
}
```
