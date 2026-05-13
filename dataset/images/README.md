This folder stores viewer-ready input assets used by the packaged HTML viewers.

- `backgrounds/` contains background images keyed by `dataset_metadata.json` filenames.
- `products/` contains product images keyed by `dataset_metadata.json` filenames.

Inputs, masks, and model outputs are expected to render directly from this package.
Viewer example order is defined by `dataset_metadata.json`; package IDs are sequential and match the packaged example numbering.
