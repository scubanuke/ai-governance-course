# How to Publish This Course on GitHub Pages

A plain-language, step-by-step guide. No coding required. You only have to do the one-time setup once; after that, updating the site is quick.

---

## What you're doing (in plain terms)

- **GitHub** is a website that will *host* your course for free.
- A **repository** ("repo") is just a project folder that lives on GitHub.
- **Pushing** / **uploading** means copying your course folder's contents up to that repo.
- **GitHub Pages** is the switch that turns the repo into a live website with its own web address.

Your files stay on your computer and in OneDrive. GitHub is a *second* copy online. Nothing is deleted from your machine.

---

## One-time setup

### Step 1 — Make a GitHub account
Go to **github.com** and sign up (free). Remember your username — it becomes part of your site's web address.

### Step 2 — Create the repository
1. Click the **+** in the top-right corner → **New repository**.
2. **Repository name:** `ai-governance-course`
3. Set it to **Public** (required for free Pages).
4. Leave the other options as-is and click **Create repository**.

### Step 3 — Upload your files
1. On the new (empty) repo page, click the link **"uploading an existing file"** (or **Add file → Upload files**).
2. On your computer, open the `ai-governance-course` folder.
3. Select **everything inside it** — the `core`, `bridge`, `branches`, `capstone`, `resources` folders and the loose files like `index.html`, `README.md`, `course-map.md`, `.nojekyll`.
   - ⚠️ **Important:** drag the *contents*, not the outer folder. `index.html` must land at the **top level** of the repo, not inside a subfolder. If you upload the outer folder by mistake, the site won't load.
4. Drag them into the browser window and wait for the upload to finish.
5. Scroll down and click the green **Commit changes** button. (That's the "push.")

### Step 4 — Turn on GitHub Pages
1. In the repo, click **Settings** (top menu).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set the branch to **main** and the folder to **/ (root)**. Click **Save**.
5. Wait about a minute. The page will show your live address:
   **`https://<your-username>.github.io/ai-governance-course/`**

That address is what you give students.

---

## Checklist (first publish)

- [ ] GitHub account created
- [ ] Public repo named `ai-governance-course`
- [ ] Uploaded the folder **contents** (index.html is at the top level)
- [ ] Committed the upload
- [ ] Pages set to `main` / `/ (root)` and saved
- [ ] Waited ~1 minute, opened the `github.io` link, confirmed it loads

---

## Updating the course later

When you change a lesson, you upload the changed file again:
1. In the repo, navigate to the file (or its folder).
2. **Add file → Upload files**, drag the new version in, **Commit changes**.
3. The live site updates within a minute — no other steps.

If you expect to edit often, install the free **GitHub Desktop** app. It links this folder to the repo so that after any edit you just click **Commit** then **Push**, and everything syncs. It saves the drag-and-drop each time.

---

## Two things that trip people up

1. **Double-clicking `index.html` on your computer won't show the site.** The page loads its lessons over the web, which browsers block for local files. It only works from the `github.io` address (or a proper local web server). This is normal — publish it and use the link.
2. **Public vs. private.** Free GitHub Pages needs the repo to be **Public**. All the course content here is meant to be shared, so Public is correct. (If you ever need a private site, that requires a paid plan.)

---

*That's it. Once it's live, the address is stable — bookmark it and share it.*
