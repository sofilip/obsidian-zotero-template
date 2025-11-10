# Purpose of the Template

The Obsidian–Zotero integration template allows you to:

- Export annotations, highlights, and attached images from Zotero into Markdown files in your Obsidian vault.

- Generate Pandoc/PDF-ready figure blocks for images from Zotero PDFs.

- Maintain consistent folder structure and absolute or relative paths for files, making the repository portable.

- Keep citekeys, figure labels, and captions automatically.

# Folder Structure in GitHub

A typical GitHub repository setup for this workflow:

MyRepo/                                  # obsidian volt
├── templates/
│   └── zotero_annotation_template.md
├── zotero_exports/                      # zotero-exported attachments
│   ├── exported_file/
│   │   └── images/
│   │       ├── img1.png
│   │       └── img2.png
│   └── file.md


## Explanation:

zotero_exports/ → stores PDFs and images exported from Zotero.

exported_file → contains Obsidian Markdown notes generated from Zotero annotations.

templates/zotero_annotation_template.md → your Jinja-style template file.

