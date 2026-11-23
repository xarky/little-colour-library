# Catalogue JavaScript — generation, validation and merging

Generate one JavaScript object for each **successfully completed** colouring page, based on the finished drawing. Use British English throughout. Generate JavaScript directly: there is no intermediate JSON correction step.

## Required schema
Each entry must have exactly these eight fields, in this order:

```javascript
{
  id: "forest-fox",
  title: "Forest Fox",
  category: "Animals",
  description: "A friendly fox explores a woodland clearing.",
  tags: ["fox", "woodland", "forest", "wildlife", "nature"],
  preview: "assets/previews/forest-fox.png",
  pdf: "assets/pdfs/forest-fox.pdf",
  alt: "Outline drawing of a fox standing in a woodland clearing"
}
```

## Metadata rules
- **ID:** Lowercase, hyphen-separated, descriptive, unique across this batch and any supplied existing catalogue. Use only `a-z`, `0-9` and hyphens; avoid leading or trailing hyphens.
- **Title:** Short, descriptive name identifying the main subject.
- **Category:** One broad category. Reuse an existing catalogue category where possible, such as Animals, Nature, Vehicles, Dinosaurs or Seasonal. If an existing catalogue is supplied, treat its actual categories as authoritative.
- **Description:** One concise, natural sentence about the drawing for parents and teachers browsing the catalogue.
- **Tags:** An array of 5–8 distinct, lowercase, relevant search terms based on the subject, setting or activity. Avoid generic terms such as `printable`.
- **Alt:** Briefly describe what is visible in the finished drawing for someone who cannot see it.
- **Paths:** Use exactly `assets/previews/<id>.png` and `assets/pdfs/<id>.pdf`; the filenames must match the generated files.
- Preserve factual accuracy: do not invent objects or activities not visible in the finished illustration.
- Use syntactically valid JavaScript strings, arrays and object literals, with no duplicate fields or malformed commas.

## Merge and output
- Collect all valid new entries in upload order, excluding failed images.
- Produce a single file named `new-catalogue-entries.js`.
- If the existing website `catalogue.js` is supplied, match its entry syntax and provide a safe append/import snippet. Do not overwrite or regenerate existing entries unless expressly requested.
- If no existing catalogue is supplied, use this standalone JavaScript structure:

```javascript
const newCatalogueEntries = [
  {
    id: "forest-fox",
    title: "Forest Fox",
    category: "Animals",
    description: "A friendly fox explores a woodland clearing.",
    tags: ["fox", "woodland", "forest", "wildlife", "nature"],
    preview: "assets/previews/forest-fox.png",
    pdf: "assets/pdfs/forest-fox.pdf",
    alt: "Outline drawing of a fox standing in a woodland clearing"
  }
];
```

This is **not** a replacement for the website's existing `catalogue.js`. It is a new-entry collection to be integrated according to the site's actual catalogue declaration.

## Final checks
1. JavaScript parses successfully.
2. Each object contains exactly the eight required fields.
3. IDs and tags are unique as specified.
4. All referenced assets exist in the output ZIP.
5. The output includes only newly generated successful entries.
