# Little Colour Library

A free, mobile-friendly colouring-page catalogue for GitHub Pages. No build step, npm, external fonts, external scripts or image hosts. The site works by opening `index.html` directly, including from a `file://` URL.

## Contents

```text
index.html                 Website design, gallery and search logic
catalogue.js               All colouring-page metadata
README.md                  This guide
assets/
  previews/                Preview images (PNG, JPG or WebP)
  pdfs/                    Print-ready A4 PDFs
```

## Included colouring pages

All four print-ready A4 PDFs are included, with PNG previews rendered from the **same PDFs**:

| Title | Category | PDF and preview base filename |
| --- | --- | --- |
| Stromboli Volcano | Nature | `stromboli-volcano` |
| Aeroplanes in South Korea | Transport | `south-korea-plane` |
| Kazakhstan Eagle | Animals | `kazakhstan-eagle` |
| Football Team with Trophy | Sport | `mirabilandia-team-photo` |

The gallery displays these four pages immediately. Category buttons are generated automatically from `catalogue.js`.

## 1. Publish using GitHub's website

1. Download the ZIP and extract it on your computer. **Upload the contents of the extracted folder**, not the ZIP or the enclosing folder.
2. Sign in to [github.com](https://github.com) and create a new **public** repository, e.g. `little-colour-library` (public GitHub Pages hosting is supported on GitHub Free).
3. Open the repository. Choose **Add file → Upload files**. Drag `index.html`, `catalogue.js`, `README.md` and the `assets` folder onto the upload area. GitHub does not preserve empty folders: create `assets/previews/` and `assets/pdfs/` when uploading the first files, if they do not appear.
4. Click **Commit changes** (normally to `main`). Check `index.html` and `catalogue.js` are at the **repository root**, not inside another directory.
5. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then **Save**.
6. Wait for deployment. Your URL will usually be `https://YOUR-USERNAME.github.io/little-colour-library/`. Visit it and refresh after the deployment completes. The four included pages should appear immediately.

GitHub Pages is a public website. Do not upload private photographs or documents without permission.

## 2. Prepare a new colouring page

1. Prepare a clear, lightweight preview image, ideally a PNG with a white background and roughly 800–1200 pixels on its longer edge. Check it looks like the actual printable page.
2. Export the **same artwork** as a PDF with **A4 page size (210 × 297 mm)**, portrait or landscape as appropriate, and generous white margins.
3. Give the two files the same lowercase, hyphenated base name, for example `forest-fox.png` and `forest-fox.pdf`. Avoid spaces, capital letters and accented characters in filenames.
4. On GitHub, navigate to `assets/previews/`, choose **Add file → Upload files**, upload the preview and commit. Repeat in `assets/pdfs/` for the PDF. If the folders do not yet exist, you can create them using **Add file → Create new file** and type `assets/previews/.gitkeep` or `assets/pdfs/.gitkeep` as the filename; commit and then upload your assets.
5. Open both uploaded files on GitHub to confirm they are the intended pair.

## 3. Edit `catalogue.js` in GitHub

1. At the repository root, open `catalogue.js` and click the pencil **Edit this file** icon.
2. Find `window.COLOUR_CATALOGUE = [` and its closing `];`.
3. Paste this **complete entry inside the square brackets** after the opening `[`. Ensure the files have already been uploaded:

```js
{
  id: 'forest-fox',
  title: 'Forest Fox',
  category: 'Animals',
  description: 'A friendly fox explores a woodland clearing.',
  tags: ['fox', 'woodland', 'forest', 'wildlife', 'nature'],
  preview: 'assets/previews/forest-fox.png',
  pdf: 'assets/pdfs/forest-fox.pdf',
  alt: 'Outline drawing of a fox standing in a woodland clearing'
},
```

4. The file should look like:

```js
window.COLOUR_CATALOGUE = [
  {
    id: 'forest-fox',
    title: 'Forest Fox',
    category: 'Animals',
    description: 'A friendly fox explores a woodland clearing.',
    tags: ['fox', 'woodland', 'forest', 'wildlife', 'nature'],
    preview: 'assets/previews/forest-fox.png',
    pdf: 'assets/pdfs/forest-fox.pdf',
    alt: 'Outline drawing of a fox standing in a woodland clearing'
  },
];
```

5. For each additional page, paste another `{ ... },` object **before** `];`. Every `id` must be unique. Keep a comma between objects; a trailing comma after the last object is allowed.

### Entries for the three requested samples

Paste these **only after uploading the matching originals** at the paths shown:

```js
{
  id: 'stromboli-volcano',
  title: 'Stromboli Volcano',
  category: 'Nature',
  description: 'A hiker looks out across the sea towards the island volcano of Stromboli.',
  tags: ['volcano', 'Stromboli', 'island', 'sea', 'hiker', 'Italy'],
  preview: 'assets/previews/stromboli-volcano.png',
  pdf: 'assets/pdfs/stromboli-volcano.pdf',
  alt: 'Outline drawing of a hiker looking towards Stromboli volcano across the sea'
},
{
  id: 'aeroplanes-in-south-korea',
  title: 'Aeroplanes in South Korea',
  category: 'Transport',
  description: 'Aeroplanes on display in a South Korean park.',
  tags: ['aeroplanes', 'aircraft', 'South Korea', 'park', 'aviation', 'transport'],
  preview: 'assets/previews/aeroplanes-in-south-korea.png',
  pdf: 'assets/pdfs/aeroplanes-in-south-korea.pdf',
  alt: 'Outline drawing of aeroplanes displayed in a South Korean park'
},
{
  id: 'kazakhstan-eagle',
  title: 'Kazakhstan Eagle',
  category: 'Animals',
  description: 'A hooded eagle overlooks a mountain lake in Kazakhstan.',
  tags: ['eagle', 'bird', 'Kazakhstan', 'mountains', 'lake', 'wildlife'],
  preview: 'assets/previews/kazakhstan-eagle.png',
  pdf: 'assets/pdfs/kazakhstan-eagle.pdf',
  alt: 'Outline drawing of a hooded eagle overlooking a mountain lake'
},
```

## 4. Categories, descriptions and tags

- Reuse an existing category by spelling it **exactly** the same, for example `Animals`, `Nature` or `Transport`.
- To create a new category, just enter a new name such as `Sports`. The website automatically adds a category filter; no HTML editing is needed.
- Keep the description to one clear sentence describing what children can colour, rather than keyword stuffing.
- Use 5–8 relevant, specific search tags, for example `['football', 'team', 'trophy', 'players', 'sport']`.
- Use British English: `colouring`, `aeroplane`, `centre`.

## 5. Commit and test

1. Click **Commit changes** and confirm the commit on `main` (or the branch selected for Pages).
2. Wait for the Pages deployment to complete, then open the live site and refresh (Ctrl+F5 on desktop if the old version is cached).
3. Check the new card shows the correct picture, title, category and description.
4. Search for the title and one tag. Select the new category filter and confirm the card appears.
5. Select **Open printable PDF**. Check the file opens and the picture matches the preview. In the PDF viewer, verify A4 paper size before printing.
6. Test on a phone and with the keyboard (Tab and Enter).

## 6. Edit, remove or troubleshoot

- **Edit:** change the relevant object's title, description, tags, category or paths in `catalogue.js`; commit.
- **Remove:** delete the whole `{ ... },` entry from `catalogue.js` and commit. Optionally delete its preview and PDF separately to free repository space.
- **Blank gallery:** confirm `catalogue.js` exists at the root, starts with `window.COLOUR_CATALOGUE = [` and ends with `];`; check quotes, commas and brackets. An empty catalogue is expected until you publish your first complete pair.
- **Broken preview or 404 PDF:** verify spelling, case and file extensions **exactly**. `forest-fox.png` is not `Forest-Fox.PNG`. Paths must be relative, like `assets/pdfs/forest-fox.pdf`, without a leading `/`.
- **Wrong picture or PDF:** compare each entry's `preview` and `pdf` base filenames; open both assets to confirm they depict the same artwork.
- **Category missing:** check that the entry's `category` is not empty, the entry has all required fields, and the JavaScript syntax is valid.
- **Search not matching:** search uses title, description, category and tags; check spelling and tag array syntax.
- **Site not updating:** confirm you committed to the published branch and root, wait for the deployment, then hard-refresh.
- **Site under repository path:** keep relative paths. Do not replace them with paths starting with `/`, which point to the domain root rather than your repository.
- **Opening locally:** double-click `index.html` in the extracted folder. `catalogue.js` is loaded with a normal script tag, so local file access does not require a web server.

The site is static: it does not collect visitor data or provide download analytics. Adding those features would require a separate service or a hosting-side integration.
