# AGENTS.md — minicourses_release public release repo

This repository contains public student-facing minicourse release artifacts.

Primary goal:
- Host stable release copies of polished minicourse materials.
- Do not invent or debug source conversions here.
- Source repair should happen upstream in the private `minicourses` source repo.

Release artifact policy:
For each public packet, prefer a matching Quarto artifact set:
- `<slug>.qmd` if source is intended to be public
- `<slug>.html`
- `<slug>.pdf`
- `<slug>_files/` if required by the HTML
- `assets/` only where required

Naming:
- Use lowercase semantic slugs with underscores.
- HTML and PDF basenames must match exactly.
- Do not expose draft/version suffixes such as `_v2` or `_v3` in canonical public filenames.
- Avoid capitalization mismatches that break GitHub Pages links.

Validation:
Before committing release artifacts, verify:
- HTML file exists.
- PDF file exists.
- required support folder exists.
- HTML “Other Formats” PDF link resolves to an existing sibling PDF.
- all paths are relative and work on GitHub Pages.
- no public link points to a missing file.
- no raw TeX macros or rough conversion artifacts appear in public HTML.

Do not:
- Do not hand-edit generated Quarto HTML except for emergency link repair explicitly requested.
- Do not publish rough Pandoc/notebook conversions as final HTML.
- Do not publish solution material unless explicitly instructed.
- Do not modify unrelated packets in the same pass.

Expected workflow:
1. Pull/copy artifacts generated upstream from the private `minicourses` repo.
2. Preserve support folders.
3. Verify links.
4. Commit focused release changes.
5. Report exact files changed and validation results.
