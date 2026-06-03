# glanyte

Static artifact distribution served via CDN at pinned release tags.

Artifacts are content-addressed (sha256) and indexed by `manifest.json`.
See internal documentation for the consuming SDK and artifact semantics.

## Layout

- `manifest.json` — index: per-entry artifact references, sha256, sizeBytes, CDN + fallback URLs.
- `detection/`, `recognition/`, `tesseract/`, `ngram/`, `dict/` — artifact categories.

## Releases

Artifacts are consumed at a pinned release tag (jsDelivr primary, GitHub Releases fallback).
