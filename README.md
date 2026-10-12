# ULTRON Android voice assistant (starter build)

A Kotlin Android app with a futuristic dark/cyan dashboard, Android text-to-speech, a speech-recognition wake-phrase loop, a microphone foreground-service notification, app-launch commands, and optional AccessibilityService home/back navigation.

## Commands in this starter
- `Hey ULTRON, open YouTube`
- `Hey ULTRON, open Chrome` / `open browser`
- `Hey ULTRON, open camera`
- `Hey ULTRON, open settings`
- `Hey ULTRON, go home`
- `Hey ULTRON, go back`
- `Hey ULTRON, what time is it?`
- `Hey ULTRON, stop listening`

## Build through GitHub Actions using a phone
1. Download and extract this ZIP on your phone.
2. On GitHub, create a new **public** repository named `ULTRON` (or choose private if you prefer; Actions usage limits may apply).
3. Upload the extracted project files and folders to the repository root, preserving `.github/workflows/build.yml`.
4. Open the repository's **Actions** tab. Select **Build ULTRON APK** and tap **Run workflow**. A push to `main` also starts a build.
5. Open the completed workflow run, scroll to **Artifacts**, and download `ULTRON-debug-apk`. Extract the artifact ZIP to get `app-debug.apk`.
6. Tap the APK in your phone's Downloads and allow installation from that source if Android asks.
7. Open ULTRON, grant microphone permission, tap **ACTIVATE ULTRON**, and keep the ongoing notification visible. For home/back commands, tap **ENABLE PHONE NAVIGATION** and enable ULTRON in Android Accessibility settings.

## Important behavior notes
- This uses Android's general-purpose SpeechRecognizer repeatedly; Android documentation says it is not intended for continuous recognition. Wake-word reliability, battery use, and background survival therefore vary by phone/recognition provider. This is a prototype, not a dedicated always-on low-power hotword engine.
- On Android 14+, microphone foreground services must be started while the app is visible and microphone permission is granted. Start listening from the app UI.
- Voice is Android TextToSpeech with a lower pitch/rate. Exact voice quality depends on installed TTS engine and voice packs; it does not include a cloned movie actor voice.
- This starter runs locally and does not include a cloud AI brain or unrestricted control of every app.
- The workflow creates a debug-signed APK for testing, not a Play Store release.
