# Trắc nghiệm trực tuyến – GitHub Pages + Firebase

## GitHub Pages
Merge branch `firebase-cloud-submissions` to `main` after reviewing. In repository Settings > Pages, choose **GitHub Actions** after adding the workflow.

## Firebase setup
1. Create Firebase project: https://console.firebase.google.com
2. Add a Web app and copy its config into `firebase-config.js`.
3. Authentication > Sign-in method: enable Email/Password.
4. Create teacher user in Authentication > Users; verify teacher email.
5. Create Firestore database in Production mode.
6. Publish `firestore.rules`. Replace `REPLACE_WITH_TEACHER_EMAIL` with the verified teacher email.
7. Check the app config values. Firebase web config is public; Firestore Rules protect the data.

## Behavior
- Students submit anonymously to `submissions`; students cannot read submissions.
- Teacher signs in with Firebase Auth; report subscribes to cloud data in real time.
- Score edits and deletions are synced.
- Teacher edits question bank in `config/quiz`; student clients load it.
- Without Firebase config, data is saved only in the browser.

## Security notes
The answer key is included in client-side code/config and can be inspected. Do not use this app for high-stakes exams. Restrict teacher access, verify Firestore rules, and consider Firebase App Check, abuse protection, and server-side grading for production.
