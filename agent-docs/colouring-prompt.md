# Colouring-page generation — fixed production prompt

For each uploaded source image independently:

Turn the uploaded image into a printable colouring page for children. Produce a downloadable A4 PDF and a downloadable PNG preview for Little Colour Library. Use British English throughout.

## Colouring page
- Keep the main subjects, poses and composition recognisable.
- Use smooth, bold black outlines on a plain white background. Close the shapes children will colour and leave their interiors white.
- Simplify faces, clothing and background details into large, open shapes that are easy to colour with crayons. Turn dark areas such as hair or clothing into outlined shapes with white interiors.
- Remove all colour, shading, shadows, textures, solid black fills and tiny details. Keep the artwork free of captions, labels and watermarks.

## Downloadable files
1. **A4 PDF** — Create a single print-ready page. Choose portrait or landscape to suit the composition and centre the whole drawing within clear white print margins.
2. **PNG preview** — Export the same finished drawing as a sharp PNG on a white background. Use a small, even margin so the artwork is easy to see in a website thumbnail. Keep the entire drawing visible.

Use the same lowercase, hyphen-separated name for both files and the catalogue ID. For example, `forest-fox.pdf` and `forest-fox.png`. The actual files must be placed at `assets/pdfs/<id>.pdf` and `assets/previews/<id>.png`.

The catalogue metadata is generated **directly as JavaScript**, following `catalogue-javascript.md`. Do not generate intermediate JSON or run a second JSON-correction prompt.
