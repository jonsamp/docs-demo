---
title: Create a new app
---

import { Collapsible } from '~/ui/components/Collapsible';
import { Terminal } from '~/ui/components/Snippet';

Before creating a new Expo app, you have to make sure that:
- Expo CLI is installed on your development machine
- Expo Go app is installed on your iOS or Android physical device or emulator

If you have not installed any of these tools, go back to the [Installation](/get-started/installation) guide before proceeding.

## Initializing the project

<Terminal cmd={[
  '# Create a project named my-app',
  '$ npx create-expo-app my-app',
  '',
  '# Navigate to the project directory',
  '$ cd my-app'
]} cmdCopy="npx create-expo-app my-app && cd my-app" />

## Starting the development server

Start the development server by running the following command:

<Terminal cmd={['$ expo start']} />

When you run `expo start` (or `npm start`), Expo CLI starts [Metro Bundler](/guides/how-expo-works/#metro-bundler). This bundler is an HTTP server that compiles the JavaScript code of your app using [Babel](https://babeljs.io/) and serves it to the Expo app. Learn more about how [Expo Development Server](/guides/how-expo-works/#expo-development-server) works.

## Opening the app on your phone/tablet

To open the app:

- On your iPhone or iPad, open the default Apple "Camera" app and scan the QR code you see in the terminal.
- On your Android device, press "Scan QR Code" on the "Home" tab of the Expo Go app and scan the QR code you see in the terminal.

You can open the project on multiple devices simultaneously. Go ahead and try it on an iPhone and Android phone at the same time if you have both handy.

<Collapsible summary="Is the app not loading on your device?">

First, make sure you are on the same Wi-Fi network on your computer and your device.

If it still doesn't work, it may be due to the router configuration &mdash; this is common for public networks. You can work around this by choosing the "Tunnel" connection type when starting the development server, then scanning the QR code again.

<Terminal cmd={['$ expo start --tunnel']} cmdCopy="expo start --tunnel" />

> Using the "Tunnel" connection type will make app reloads considerably slower than on "LAN" or "Local", so it's best to avoid tunnel when possible. You may want to install a simulator/emulator to speed up development if "Tunnel" is required for accessing your machine from another device on your network.

</Collapsible>

<Collapsible summary="Using a simulator or emulator?">

If you are using a simulator or emulator, you may find the following Expo CLI keyboard shortcuts to be useful to open the app on any of the following platforms:

- Pressing `i` will open in an [iOS simulator](/workflow/ios-simulator).
- Pressing `a` will open in an [Android Emulator or connected device](/workflow/android-studio-emulator).
- Pressing `w` will open in a web browser. Expo supports all major browsers.

</Collapsible>

## Making your first change

Open **App.js** file in your code editor and change the text to "Hello, world!". You are going to see it update on your device. This is great progress! You now have the Expo toolchain running on your machine, can edit the source code for a project, and see the changes live on your device.

<Collapsible summary="Are the changes not showing up on your device?">

Expo Go is configured by default to automatically reload the app whenever a file is changed, but let's make sure to go over the steps to enable it in case somehow things aren't working.

- Make sure the you have the [development mode enabled in Expo CLI](/workflow/development-mode#development-mode).
- Close the Expo app and reopen it.
- Once the app is open again, shake your device to reveal the developer menu. If you are using an emulator, press `⌘+d` for iOS or `ctrl+m` for Android.
- If you see `Enable Fast Refresh`, press it. If you see `Disable Fast Refresh`, dismiss the developer menu. Now try making another change.

  ![In-app developer menu](/static/images/developer-menu.png)

</Collapsible>

## Up next

Let's face it. You are going to make mistakes and typos and you are going to get warnings and errors in your app. So [let's learn a little bit about how to read and interpret errors](/get-started/errors).
