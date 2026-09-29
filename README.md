# Alex AI — Android cloud-build project

This project is prepared for a **phone-only cloud build** using GitHub Actions. You do not need Android Studio, a computer, or Termux.

## Build the APK from your Android phone

1. Create/sign in to a GitHub account.
2. Create a **new repository**. A private repository is recommended.
3. Upload the contents of this `alex_android` folder to the repository (including `.github/workflows/build-apk.yml`).
4. Open the repository's **Actions** tab.
5. Select **Build Alex AI APK**.
6. Tap **Run workflow** if you want to start it manually.
7. Wait for the workflow to finish successfully.
8. Open the completed workflow run and find **Artifacts**.
9. Download **Alex-AI-debug-apk** and extract it.
10. Install `app-debug.apk` on your Android phone. Android may ask you to allow installation from your browser/file manager.

The workflow uses a GitHub-hosted Ubuntu runner to install the Android SDK and compile the Gradle project, then uploads the APK as a workflow artifact.

## Connect your AI backend

Open:

`app/src/main/assets/index.html`

Find:

`https://YOUR-SERVER.example/api/chat`

Replace it with your own HTTPS backend endpoint, then commit the change and run the workflow again.

**Never put your OpenAI API key in this Android project or inside the APK.** Keep the key on your private backend server. The Android app should call your backend, and your backend should call OpenAI.

## Features

- Alex AI chat interface
- Study mode flag
- Voice input where supported
- Read replies aloud
- Clear chat
- HTTPS backend connection
- Debug APK produced automatically by GitHub Actions
