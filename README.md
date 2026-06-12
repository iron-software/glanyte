# glanyte

Static OCR model-artifact distribution for Universal.IronOcr, served from
**GitHub Release assets** at pinned release tags.

Artifacts are content-addressed (sha256) and indexed by `manifest.json`. See
internal documentation for the consuming SDK and artifact semantics.

## Where the artifacts live

Model binaries are distributed **only as GitHub Release assets** — they are
**not** committed to the git tree (binaries in git history are unbounded and
unrecoverable; release assets are deletable and re-uploadable). Browse and
download them from the repository's **Releases** page, or fetch directly:

```
https://github.com/iron-software/glanyte/releases/download/<tag>/<filename>
```

Release assets are a flat namespace (bare filenames, no folders). The local
on-disk layout the consuming SDK writes (e.g. `recognition/…`, `ngram/…`,
`licensePlate/…`) is dictated by each entry's `filename` in `manifest.json`,
not by the asset name.

## Index

- `manifest.json` — the authoritative index: per-entry artifact references
  (`filename`, `sha256`, `sizeBytes`, download URL + optional fallback),
  per-language model coverage, and the executable init plan.

## Releases

Consumed at a pinned release tag. `manifest.json` is itself published as a
release asset, so the index and the artifacts it points to ship together.
