# Hunterline for Android

This folder is the source of the Hunterline phone app. It is not an APK yet.
An APK has to be built with Android's tools, so pick one of the two ways below.

The app works offline. It stores everything on your phone, and the characters use
built-in lines when there is no connection. If you add your own Anthropic API key
in the app (Me tab, Settings), characters reply live whenever you are online.

## Way 1: build it online with GitHub (no coding, about 10 minutes)

1. Make a free account at github.com and click New repository. Name it `hunterline`. Private is fine.
2. On the new repository page click "uploading an existing file". Drag in everything
   from this folder except the `.github` folder (it is usually hidden and often skipped).
3. Still on GitHub, click Add file, then Create new file. In the name box type
   `.github/workflows/build-apk.yml` (typing the slashes makes the folders).
   Open `build-apk.yml` from this folder in any text app, copy everything, paste it
   into the big box, and click Commit changes.
4. Open the Actions tab. Pick "Build Hunterline APK", click Run workflow. The first build takes a few minutes.
   If it started on its own after step 3, that works too.
5. When the run shows a green tick, open it. At the bottom under Artifacts, download
   `Hunterline-apk`. Unzip it to get `app-debug.apk`.
6. Send `app-debug.apk` to your phone, open it, and allow "Install unknown apps" for
   the app you opened it from when Android asks. Then install.

## Way 2: build it on a computer with Android Studio

1. Install Android Studio (free, from developer.android.com).
2. Choose Open and select this folder. Let it finish syncing.
3. Choose Build, then Build APK(s). Android Studio shows a link to `app-debug.apk` when it is done.

## What is inside

- `app/src/main/assets/www/index.html` is the whole app. Edit it to change the app.
- `app/src/main/java/app/hunterline/MainActivity.java` shows it full screen, opens the
  picture chooser for avatars, and handles the Back button.

## Good to know

- Your profile, posts and chats stay on the phone. Uninstalling the app removes them.
- The API key is saved on the phone only and is sent only to Anthropic. Usage is billed to your API account, separately from any Claude subscription.
- This is a debug build for your own use. A Play Store release needs signing and a store listing.
- Fonts load from Google Fonts when you are online. Offline, the app uses your phone's default font.
- The project was written and checked by reading and a stand-in compile, but it has not been built on a real Android toolchain yet. If a step fails, copy the error text and ask for a fix.
