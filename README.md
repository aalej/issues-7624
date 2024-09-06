# Repro for issue 7624

## Versions

firebase-tools: v13.16.0<br>
platform: macOS

## Steps to reproduce

1. Install dependencies
   - Run `npm i`
   - Run `cd functions`
   - Run `npm i`
2. Run `firebase emulators:exec "npm run test" --project dev`
   - Outputs:

```
⚠  emulators: You are not currently authenticated so some features may not work correctly. Please run firebase login to authenticate the CLI.
i  emulators: Starting emulators: auth, functions, firestore, hosting, pubsub
⚠  functions: The following emulators are not running, calls to these services from the Functions emulator will affect production: database, storage, dataconnect
⚠  functions: You are not signed in to the Firebase CLI. If you have authorized this machine using gcloud application-default credentials those may be discovered and used to access production services.
⚠  functions: Unable to fetch project Admin SDK configuration, Admin SDK behavior in Cloud Functions emulator may be incorrect.
i  firestore: Firestore Emulator logging to firestore-debug.log
✔  firestore: Firestore Emulator UI websocket is running on 9150.
i  pubsub: Pub/Sub Emulator logging to pubsub-debug.log
⚠  hosting: Could not fetch web app configuration and there is no cached configuration on this machine. Check your internet connection and make sure you are authenticated. To continue, you must call firebase.initializeApp({...}) in your code before using Firebase.
i  hosting[projectname-dev]: Serving hosting files from: public
✔  hosting[projectname-dev]: Local server: http://127.0.0.1:5000
i  functions: Watching "/Users/alejandromarco/Desktop/firebase-tools/issues/7624/functions" for Cloud Functions...
⚠  functions: Your requested "node" version "18" doesn't match your global version "20". Using node@20 from host.
Serving at port 8843

✔  functions: Loaded functions definitions from source: .
i  Running script: npm run test

> 7624@1.0.0 test
> jest -- "__tests__/"


 PASS  __tests__/index.test.js
  ✓ should add 1 + 1 (1 ms)
  ✓ should get a response from hosting emulator (25 ms)

Test Suites: 1 passed, 1 total
Tests:       2 passed, 2 total
Snapshots:   0 total
Time:        0.188 s, estimated 1 s
Ran all test suites matching /__tests__\//i.
✔  Script exited successfully (code 0)
i  emulators: Shutting down emulators.
i  functions: Stopping Functions Emulator
i  hosting: Stopping Hosting Emulator
i  firestore: Stopping Firestore Emulator
i  pubsub: Stopping Pub/Sub Emulator
i  auth: Stopping Authentication Emulator
i  eventarc: Stopping Eventarc Emulator
i  tasks: Stopping Cloud Tasks Emulator
i  hub: Stopping emulator hub
i  logging: Stopping Logging Emulator
```
