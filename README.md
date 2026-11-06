# Quest Ledger

A D&D 5e companion for phones, tablets and laptops: character builder and sheets, spells, items with attunement, 3D dice, conditions that do the math, achievements, D&D Beyond import, and DM tools (The Tavern shared table, monster tracker, maps with fog and walls, XP, buffs, pranks).

Players sign in with Google. Characters save to their account and show up on every device.

## 1. Put it on GitHub Pages
1. Create a new repository named `quest-ledger` on github.com.
2. Upload every file in this folder (Add file › Upload files › Commit). `.nojekyll` is hidden on a Mac: press Cmd+Shift+. in Finder to see it.
3. Settings › Pages › Source: "Deploy from a branch", branch `main`, folder `/ (root)` › Save.
4. Your site: `https://<your-username>.github.io/quest-ledger/`

Without step 2 below, the site works with no sign-in (characters save in that browser only, no Tavern).

## 2. Turn on Google sign-in (Firebase, free)
1. Go to https://console.firebase.google.com and click **Create a project**. Name it `quest-ledger`. Google Analytics can be off.
2. **Build › Authentication › Get started › Sign-in method › Google › Enable**. Pick your email as the support email and **Save**.
3. Still in Authentication: **Settings › Authorized domains › Add domain** › `<your-username>.github.io`.
4. **Build › Firestore Database › Create database**. Pick a location near you (for example `us-central`) and **Start in production mode**.
5. Firestore **Rules** tab: delete everything, paste the contents of `firestore.rules`, click **Publish**.
6. Project Overview (gear icon) › **Project settings** › Your apps › click the **</>** (Web) icon. Nickname `quest-ledger`, no hosting, **Register app**.
7. Copy the values from the `firebaseConfig` it shows (apiKey, authDomain, projectId, storageBucket, messagingSenderId, appId).
8. On GitHub, open `firebase-config.js`, click the pencil, paste the values between the quotes, **Commit changes**.
9. Wait a minute, open your site, tap **Sign in with Google**.

## Limits on the free plan
50,000 reads and 20,000 writes a day, and 1 GB of storage. Plenty for a gaming group. A busy session uses a few thousand.

## Moving characters
Use **Export** on the Characters page to save a file, and **Import** on the other device or site. Import also reads D&D Beyond character data (.json) and character sheet PDFs.

## Credits
Rules content from the System Reference Document 5.1 by Wizards of the Coast, licensed under CC-BY-4.0.
