# Civil 3D Object Name Generator

Browser-based tool for generating consistent Civil 3D object names from a project-specific Excel workbook.

## What it does

Two variants of the same tool, served from one site:

| Page | Name format |
|---|---|
| [`name-generator.html`](name-generator.html) | `State-Function-Type-Location-Name` |
| [`name-generator-variant.html`](name-generator-variant.html) | `State-Function-Type-Location-Variant-Name` |

- Dropdowns are populated from the project workbook, so codes are always consistent with the project's naming register.
- The free-text Name part is converted to uppercase, spaces become underscores, and invalid characters are removed.
- Copy a name to the clipboard, collect names in a batch list and download them as a `.txt` file.
- The loaded workbook and recent names are cached in the browser's local storage, so you only load the workbook once per project. Use **Change Workbook** when it changes.

Variant codes used in the sample: `ALL` (common to all variants), `SPC` (specimen design), `O01`–`O04` (options 1–4). The option codes use the letter O, not zero.

## How to use

1. Open the site (GitHub Pages) or `index.html` and choose a variant.
2. Click **Choose file** and load your project workbook (`.xlsx`).
3. Select State, Function, Type, Location (and Variant), then type the descriptive Name.
4. Click **Copy**, or **Add to List** to build a batch.

### Workbook layout

Sheet 1 only, laid out as in the files in [`templates/`](templates/):

- `A1` = `Project Name`, `B1` = the project name
- Sections stacked vertically, in this order: `State`, `Function`, `Type`, `Location` (then `Variant` for the variant tool)
- Each section is a heading row, then a `Label | Code` header row, then the entries
- No blank rows inside a section; blank rows between sections are fine

The sample workbooks use a placeholder project and generic location codes. Keep real project workbooks out of this public repo.

## Files

| Path | Purpose |
|---|---|
| `index.html` | Landing page linking both variants |
| `name-generator.html` | Five-part tool. Reads Excel via SheetJS in `vendor/` |
| `name-generator-variant.html` | Six-part tool with Variant. Has a built-in XLSX reader, so it needs no other files |
| `templates/` | Sample workbooks for each variant |
| `vendor/xlsx.full.min.js` | SheetJS Community Edition 0.18.5 (Apache-2.0, see `vendor/xlsx.LICENSE`) |
| `docs/version-history.md` | Recovered development history |

## Changelog

See [CHANGELOG.md](CHANGELOG.md).
