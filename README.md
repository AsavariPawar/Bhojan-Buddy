# Bhojan Buddy🍲

This version uses **one HTML file** and Firebase's browser SDK from a CDN. You do not need Node.js, npm, React, or a build step. Internet is required for Firebase and the fonts.

## Run locally
1. Extract the ZIP.
2. Open `index.html` in VS Code or double-click it to open in a browser.
3. To use login/database, first configure Firebase as below.

## Firebase setup
1. Create a project at https://console.firebase.google.com/
2. In Project settings → General, register a Web app and copy the configuration.
3. Open `index.html` in VS Code. Near the bottom, find `const firebaseConfig = { ... }`.
4. Replace all `PASTE_..._HERE` values with your actual Firebase web app values.
5. Authentication → Sign-in method → enable Email/Password.
6. Create a Cloud Firestore database.
7. In Firestore → Rules, paste `firestore.rules` and Publish.
8. Save `index.html`, then refresh the browser.

Firebase web config is designed to be used in browser apps. Security must be enforced by Firestore Rules; never add service account keys/private keys here.

## Create organizer
Register a normal account first and sign in once. In Firestore → `users`, open the document whose ID matches the organizer's Firebase Auth UID and change `role` from `student` to `organizer`. Sign out and back in. Do not allow public users to choose their own organizer role.

## GitHub Pages
1. Create a public repository such as `bhojan-buddy`.
2. Upload `index.html`, `firestore.rules`, and `README.md`.
3. In repository Settings → Pages, choose deploy from branch `main`, folder `/ (root)`.
4. Save and wait for the published URL.
5. In Firebase Authentication → Settings → Authorized domains, add the GitHub Pages domain if required.

## Features
- Student registration/sign-in
- Menu by date and meal slot
- Confirm/cancel meal selections
- Organizer menu publishing/updating
- Organizer response counts and CSV export
- Responsive green and cream layout

## Notes
- Menu selections currently can be changed at any time. A production app should enforce cutoff times through trusted backend logic/rules.
- This is a starter app. Test the rules and workflows with two test accounts before using real hostel data.
