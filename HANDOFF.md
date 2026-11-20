# Samantha's portfolio — handoff guide

Everything you need is in this folder. The whole site is one file, `index.html`, plus an `images/` folder. No build tools, no frameworks, nothing to install.

```
index.html        the entire site
images/           photos (headshot.jpg is already here)
HANDOFF.md        this guide
```

---

## 1. Look at it right now

Double-click `index.html`. It opens in your browser and works completely offline. Any change you make, save the file and refresh the page.

---

## 1½. Edit it right in the browser (no code)

Double-click `index.html`. A **✎ Edit page** button sits at the bottom of the screen. Click it, then:

- **Text** — click any heading, paragraph, button label, skill or date and type. In a list (skills, bullet points), **Enter** adds a new item and **Backspace** on an empty one removes it.
- **Photos** — click the headshot or the polaroid and pick a new picture. It's shrunk and stored inside `index.html`, so you don't need to put it in `images/`.
- **Links** — click a link (Résumé, LinkedIn, ResearchGate, nav) to change where it goes. For your résumé, put the PDF next to `index.html` and type its file name, e.g. `resume.pdf`.
- **Journey map and chip labels** — click a label on a drawing to retype it.
- **Projects** — the **Projects** button (or clicking any project card) opens a panel to add, reorder, delete or change projects, including their photos.
- **Thesis stops** — the **Thesis stops** button (or clicking a numbered pin) does the same for the chip walkthrough.

When you're done, click **Save a copy** (or Ctrl+S / Cmd+S). Your browser downloads a new `index.html` — **replace the old one with it** (and upload it to GitHub if the site is online). Until then your edits are kept as a draft in that browser; if you close the tab and come back, it offers to bring them back.

On the live website visitors never see the edit button. To edit there anyway, add `?edit` to the end of the address, or press Ctrl+Shift+E (Cmd+Shift+E on Mac) — but you'll still need to upload the saved copy for the change to go live.

---

## 2. Put it online with GitHub Pages (free)

This gives you a public address like `samanthaomer.github.io`.

1. Make a free account at **github.com** if you don't have one.
2. Click the **+** in the top right → **New repository**.
3. Name it exactly `yourusername.github.io` — for example, if your username is `somer`, name the repository `somer.github.io`. Set it to **Public**. Click **Create repository**.
4. On the new repository page, click **uploading an existing file**.
5. Drag in `index.html` **and** the whole `images` folder. Click **Commit changes**.
6. Go to **Settings → Pages**. Under "Branch", pick `main` and `/ (root)`, then **Save**.
7. Wait about a minute, then visit `https://yourusername.github.io`. That's your live site.

Every time you upload a new `index.html`, the live site updates within a minute.

---

## 3. Let Claude edit the site for you

Once the repository exists, you can connect it to Claude and then just ask for changes in plain English instead of editing HTML yourself.

1. Go to **https://claude.ai/connect-github** and sign in with your GitHub account.
2. You'll be asked to install the **Claude GitHub App**. Choose **Only select repositories** and pick your `yourusername.github.io` repository.
3. Back in Claude, start a new chat and say which repository to work in. From then on Claude can read the site, make a change, and open a pull request you approve on GitHub.

A good first message to Claude:

> I have a one-file portfolio site in my GitHub repo `yourusername.github.io`. The whole site is `index.html`. Please read it, then add a new project called "..." to the PROJECTS list near the bottom of the file, following the same shape as the existing entries.

You don't have to connect GitHub at all if you'd rather edit the file by hand — sections 4 and 5 cover that.

---

## 4. Adding a project

Open `index.html` in any text editor and search for `const PROJECTS`. It's a list near the bottom. Copy one of the existing blocks and change the text:

```js
{ title: "Name of the project", tag: "Projects", icon: "ico-sun",
  photo: "images/my-project.jpg",
  summary: "One or two sentences that appear on the card and at the top of the case study.",
  problem: "What was hard or unsolved.",
  role: "Your title: what you actually did.",
  results: ["A result", "Another result"],
  tools: ["AutoCAD", "COMSOL"] },
```

Notes:

- **Keep the commas.** Each project block ends with a comma except the last one in the list.
- **`tag`** is what the filter buttons use. Use `"Projects"`, `"Process"` or `"Publication"` to reuse an existing filter, or type a new word and a new filter button appears on its own.
- **`icon`** is the line drawing shown when there is no photo. Pick from `ico-sun`, `ico-arches`, `ico-sprout`, `ico-spiral`.
- **`photo`** is optional. Leave the line out entirely and you get the icon instead.
- You can also add `blurb: "shorter text for the card"` if the summary is long, and `next: "What comes next for this project."`

---

## 5. Adding pictures

Drop image files into the `images/` folder and point to them by name.

| What | File name | Where it shows |
|---|---|---|
| Headshot | `images/headshot.jpg` | The arch on the opening page |
| Snapshot | `images/snapshot.jpg` | The small polaroid further down |
| Project photo | anything, e.g. `images/chip.jpg` | That project's card and case study — add `photo: "images/chip.jpg"` to the project |

If a picture is missing or the name is misspelled, the site quietly falls back to the line drawing instead of showing a broken image, so nothing ever looks broken while you're working.

Keep photos under about 1 MB each so the page stays fast. JPG or PNG both work. Landscape photos suit the project cards best.

---

## 6. Other things that are easy to change

Search `index.html` for the text you want to change — it's all in plain words:

- **Name, title, bio** — search for `SAMANTHA` near the top of the page body.
- **Email** — search for `Samanthaomer3@gmail.com`.
- **Skills** — search for `skill-tags`. Each skill is one `<li>Skill name</li>`. Add or remove them freely; the cards resize themselves.
- **Journey map** — search for `CAL POLY POMONA`. Each stop is a `<text>` line with the year and place, and a `class="sub"` line under it with the role.
- **Thesis stops** — search for `const STOPS`. Each numbered stop on the chip has a title, a paragraph and a few bullet points.
- **Résumé button** — search for `Résumé (PDF)` and put your PDF's file name in the `href`, after adding the PDF to the folder.

---

## 7. If something breaks

The site is one file, so the safest habit is: before a big edit, save a copy of `index.html` as `index-backup.html`. If an edit goes wrong, swap the backup back in.

A missing comma or quote mark in the `PROJECTS` list is the usual cause of a blank Studio section. If that happens, undo your last edit and try again one line at a time.
