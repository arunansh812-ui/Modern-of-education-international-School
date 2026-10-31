MEIS FIREBASE + HOME-SCREEN STARTER
This is a NEW limited starter, not the full original school management application. It supports public, live-synced text circulars and an email/password administrator login. Do not upload real student records to it.

1. Create your own Firebase project at https://console.firebase.google.com/ (with a parent/guardian or school administrator if needed).
2. In Project Settings > Your apps, register a Web app and copy its Firebase config fields into firebase-config.js. Do not put service account/private keys here.
3. Under Build > Authentication > Sign-in method, enable Email/Password. In Authentication > Users, add an administrator user and copy that user's UID.
4. Under Build > Firestore Database, create a database. Under Rules, replace the default rules with the contents of firestore.rules and Publish.
5. In Firestore > Data, create a collection named admins, document ID exactly equal to the administrator's Authentication UID, and a boolean field named enabled set to true. Never add public create rules for admins.
6. Host the entire folder over HTTPS (for example, Firebase Hosting). Do not just open index.html as file://; ES modules and the service worker require web hosting. Firebase Hosting CLI instructions: https://firebase.google.com/docs/hosting/quickstart . Set the hosting public directory to this folder, and avoid overwriting index.html when prompted.
7. Open the HTTPS URL in Chrome on Android. Chrome menu > Add to Home screen / Install app. Some browsers may show Add shortcut instead of Install app; SVG icon support varies by browser.
8. Log in using the admin account and publish a test circular. Open the same hosted URL on a second device to see the same saved announcement.

IMPORTANT: The Firebase project is not yet connected. This package cannot sync data until you complete steps 1-6. Treat circulars as public information. Firestore rules, not just the UI, enforce write permissions. No staff/student portals or uploads are enabled in this starter. Keep account passwords private.
