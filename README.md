# SIT Lost & Found

A responsive campus lost-and-found board built with HTML, CSS, JavaScript, Firebase Authentication, and Cloud Firestore. This is a student project; it uses anonymous Firebase sign-in and does not verify student identity.

## Features

- Post lost and found items with an optional photo
- Search and filter the shared item board
- Submit and review claim messages
- Restrictive Firestore rules keep reporter contact details and claims private to the relevant users
- Mobile layout with animated sample item cards

## Run with your own Firebase project

1. Create a Firebase project and register a Web App.
2. Enable **Authentication → Sign-in method → Anonymous**.
3. Create a Cloud Firestore database.
4. Copy `firebase-config.example.js` to `firebase-config.js` and fill in your own Firebase Web App configuration. The local config file is ignored by Git.
5. Install the Firebase CLI with Node.js: `npm install -g firebase-tools`.
6. Open a terminal in this folder and run `firebase login` followed by `firebase use --add`. Select your own project.
7. Deploy the Hosting site and Firestore rules:

   ```text
   firebase deploy --only hosting,firestore:rules
   ```

8. Open the Hosting URL and test posting and claiming with two separate browser sessions.

No build step is required. `index.html` loads `firebase-config.js` and `app.js` directly.

## Data and security notes

Firebase Web App settings are browser-visible, so use your own Firebase project and keep Firestore rules enabled. The rules in `firestore.rules` require Firebase Authentication and limit changes to the owning user. Reporter email and PIN are stored separately from public item records; claim messages are limited to the claimant and item owner. Email is not sent automatically. Anonymous sign-in does not establish a user's SIT identity. Do not use real personal information in public demonstrations.

## Project files

- `index.html` — page structure, styling, responsive layout, and logo
- `app.js` — Firebase Auth, Firestore, item board, and claims
- `firebase-config.example.js` — template for your own local Firebase configuration
- `firestore.rules` — Firestore access controls
- `firebase.json` — Firebase Hosting and rules deployment settings
- `sit-logo.png` — campus logo asset
"# SIT-Lost-and-Found" 
"# SIT-Lost-and-Found" 
