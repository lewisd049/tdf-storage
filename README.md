# Storage Portal

A GitHub Pages dashboard for recording storage plans, customer allocations, usage and payments. It is a tracker only: it never connects to, changes, or limits anyone's disk storage.

## Deploy

1. Create a Firebase project and add a **Web app** in its console.
2. Enable **Cloud Firestore**. For an initial private setup, Firebase's test mode lets you confirm the app works. Do not leave test-mode rules enabled on a public GitHub Pages site: they allow anyone to read and edit the data. The included `firestore.rules` is a safe starting point once Firebase Authentication is added.
3. Copy `firebase-config.example.js` to `firebase-config.js`, and replace every placeholder with the Firebase configuration values Firebase gives you.
4. Upload the contents of this folder to a GitHub repository. In repository **Settings → Pages**, deploy from the `main` branch and the `/ (root)` folder.

The app uses these Firestore collections: `users`, `plans`, `payments`, and `settings` (document `portal`). Firebase's configuration object is intentionally not a secret, but Firestore rules are essential. For a personal admin-only portal, require Firebase Authentication in the rules before making it public.

## Pages

- `/` dashboard
- `/users/` customer allocations, usage and search
- `/plans/` storage-plan management
- `/payments/` payment history and recording
- `/settings/` portal settings and Firebase connection check
