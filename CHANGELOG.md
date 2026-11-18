# Changelog

All notable changes to this project are documented here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- Five-part generator (`name-generator.html`) and Variant generator (`name-generator-variant.html`), from the August 2026 versions.
- Landing page, sample workbooks for both variants, README, version history and repo scaffold.
- Vendored SheetJS 0.18.5 so the five-part generator no longer depends on a missing `_files` folder.

### Changed
- Both pages reset to a clean start state: the snapshot of another project's dropdowns and recent names, saved with the page, has been removed. No JavaScript was changed.
