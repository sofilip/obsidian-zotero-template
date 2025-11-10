# Purpose of the Template

The Obsidian–Zotero integration template allows you to:

- Export annotations, highlights, and attached images from Zotero into Markdown files in your Obsidian vault.

- Uses the Zotero comments as sections, and .

- Generate Pandoc/PDF-ready figure blocks for images from Zotero PDFs.

- Maintain consistent folder structure and absolute or relative paths for files, making the repository portable.

- Keep citekeys, figure labels, and captions automatically.

# Folder Structure in GitHub

A typical GitHub repository setup for this workflow:

```
MyRepo/                                  # obsidian volt
├── _templates/
│   └── zotero_annotation_template.md
├── zotero_exports/                      # zotero-exported attachments
│   ├── exported_file/
│   │   └── images/
│   │       ├── img1.png
│   │       └── img2.png
│   └── file.md
```

## Explanation

zotero_exports/ → stores PDFs and images exported from Zotero.

exported_file → contains Obsidian Markdown notes generated from Zotero annotations.

templates/zotero_annotation_template.md → your Jinja-style template file.

# Usage

  1. Place the template.md in your obsidian /_templates folder.

  2. Configure your Obsidian–Zotero plugin.

  3. Add a new Format:
     
    - Name: format_name
    - Output path: zotero_exports/{{citekey}}/{{citekey}}.md
    - Image output path: zotero_exports/{{citekey}}/images/
    - Image Base Name: {{citekey}}
    - Template file: _templates/zotero_annotation_template.md
    - Bibliography style: IEEE (use whatever you want, don't forget to change the .csl file)
   
  5. Use the Zotero Integration Plugin (ctrl+p), in Obsidian, and select the file you'd like to export, type the format_name you entered.

> Note: I used the preconfigured Zotero template.tex for the example.pdf
