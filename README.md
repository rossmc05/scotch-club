# 🥃 Scotch Club

A shared tasting map and bottle log for Andrew, Matt, Pat and Ross.
The page is one file (`index.html`) hosted on GitHub Pages; the bottles live in
Firebase (Firestore), so everyone with the link sees the same list, live.

## Files

- **`index.html`**: the whole website (Firebase config already inside)
- **`firestore.rules`**: database rules to paste into Firebase (Part 6)
- **`README.md`**: this guide

---

## Part 5: Put it on GitHub

1. Go to **github.com** → **+** (top right) → **New repository**.
2. Name it `scotch-club`. Set it to **Public** (GitHub Pages is free for public repos;
   the Firebase config is not a secret, the rules protect the data). → **Create repository**.
3. On the new repo page click **uploading an existing file**.
4. Drag in `index.html`, `firestore.rules` and `README.md` → **Commit changes**.
5. Go to **Settings → Pages**.
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)** → **Save**
6. Wait 1–2 minutes and refresh. The site link appears at the top:
   `https://<your-username>.github.io/scotch-club/`
7. Open it. The first time anyone opens it, the 56 bottles load automatically.

## Part 6: Lock down the database

Test mode lets anyone do anything and **expires after 30 days**, so do this once the site works.

1. Firebase console → **Firestore** → **Rules** tab.
2. Delete everything there and paste the contents of `firestore.rules`.
3. Click **Publish**.

What the rules allow: anyone with the link can view, add, edit and delete bottles,
and add distilleries. They block junk data (wrong fields, huge text) and stop
distilleries from being deleted.

## Part 7: Test it

1. On your phone, open the link and add a test bottle.
2. Check it appears on your computer within a second or two.
3. Click it → **Delete**.
4. Send the link to the group. Tip: on a phone, use "Add to Home Screen" so it opens like an app.

---

## Updating the site later

Edit `index.html` and upload it again to the repo (Add file → Upload files, same name).
GitHub Pages republishes in about a minute. The bottles are in Firebase, not the file,
so updating the page never loses data.

**Adding a member:** in `index.html`, find `const HOSTS = [` and add the name.

**Backup:** the **Download CSV** button on the page exports the whole log.
