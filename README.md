# Hearthwood Library

A walnut bookshelf for your personal library, in a single web page.

- Add books by title and author; **Find book info** looks them up on [Open Library](https://openlibrary.org).
- Real cover art loads straight from Open Library's cover service. You can swap in a photo of your own copy.
- Books are shelved by genre, chosen from Open Library's public subject tags. Romance has its own wing:
  Contemporary, Romantic Comedy, Dark Romance, Romantic Suspense, Romantasy, Paranormal, Historical, Sports, LGBTQ+.
  Each book's card says which tags decided its shelf, and you can move it by hand.
- Rate books 1–5 stars, keep notes, sort and search, and switch between a covers view and a spines view.

## Your data

Everything is saved in your browser's local storage on the device you use. Use **Download backup** to save
a copy and **Restore backup** to load it in another browser.

## Sync between your phone and computer

**Sync** keeps one shelf on all your devices. They share one file, `hearthwood-library.json`, kept on a
separate `hearthwood-data` branch of a GitHub repository. This website's own repository works. Because the
data lives on its own branch, syncing never changes `main` or rebuilds the site. It works in a phone browser.

1. Make a fine-grained access token at <https://github.com/settings/personal-access-tokens/new>.
   Under **Repository access** choose **Only select repositories** and pick `hearthwood-library`.
   Under **Permissions → Contents** choose **Read and write**. It needs nothing else.
2. On the site, press **Sync**. The repository is filled in for you. Paste the token and press **Save and sync**.
   The `hearthwood-data` branch is created the first time.
3. Do step 2 on your other device. The shelf comes down from GitHub.

**This repository is public, so anyone can read the shelf file**, including ratings, notes and any cover
photos you took. The page warns you once before it uses a public repository. If you'd rather keep the
shelf to yourself, use a private repository instead. Setup is the same.

The dot on the Sync button shows the state: green is up to date, gold means changes are waiting to be
sent, red needs your attention. **Sync automatically** (off by default) checks GitHub when the page
opens and saves a few seconds after each change. Each save is a commit on the `hearthwood-data` branch.

If both devices changed the shelf before syncing, nothing is overwritten. You choose this device's
shelf, GitHub's shelf, or a combination of both. The shelf you don't keep is downloaded as a backup file first.

The token is stored only in each browser you set up and never goes into backups. It can change files in the
repository it's given, which here includes the website. Any other page you publish on the same `github.io`
address could read it in that browser. If it might have leaked, delete it on GitHub and make a new one.
