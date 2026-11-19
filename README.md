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

**Sync** keeps one shelf on all your devices. They share one file, `hearthwood-library.json`, in a
**private** GitHub repository you own. Nothing else is involved, and it works in a phone browser.

1. Make a new private repository, for example `hearthwood-data`. Don't use this website's repository: it's public.
2. Make a fine-grained access token at <https://github.com/settings/personal-access-tokens/new>.
   Under **Repository access** choose **Only select repositories** and pick the data repository.
   Under **Permissions → Contents** choose **Read and write**. It needs nothing else.
3. On the site, press **Sync**, enter `your-name/hearthwood-data`, paste the token and press **Save and sync**.
4. Do step 3 on your other device. The shelf comes down from GitHub.

The dot on the Sync button shows the state: green is up to date, gold means changes are waiting to be
sent, red needs your attention. **Sync automatically** (off by default) checks GitHub when the page
opens and saves a few seconds after each change. Each save is a commit in the data repository.

If both devices changed the shelf before syncing, nothing is overwritten. You choose this device's
shelf, GitHub's shelf, or a combination of both. The shelf you don't keep is downloaded as a backup file first.

The token is stored only in each browser you set up and never goes into backups. Any other page you
publish on the same `github.io` address could read it in that browser, so keep the token limited to
the data repository. If it might have leaked, delete it on GitHub and make a new one.

## Running it

It's one file, `index.html`, with no build step. Open it in a browser, or visit the GitHub Pages site.
