# CatalogStitch-Eval Dataset

An evaluation dataset for catalog image compositing with dimension mismatch and occlusion scenarios.

## License

This dataset is released under the [Adobe Research License](LICENSE.md) for noncommercial research purposes only. See [`LICENSE.md`](LICENSE.md) for the full license text and third-party image licensing details.

## Dataset Overview

| Category | Count | Description |
|----------|-------|-------------|
| Dimension-Aware | 35 | Product replacement with significant aspect ratio differences |
| Occlusion | 23 | Scenes with 1-2 foreground occluders |
| **Total** | **58** | |

## Dataset Structure

```
CatalogStitch-Eval/
├── README.md                    # This file
├── LICENSE.md                   # License information
├── dataset_metadata.json       # Full metadata with source URLs
├── free_license_report.json    # License verification report
├── index.html                  # Landing page for HTML viewers
├── masks/                       # Pre-computed masks (our contribution)
│   ├── stitch/
│   └── occlusion/
├── results/                     # Compositing results
│   ├── stitch/
│   │   └── index.html          # Dimension-aware HTML viewer
│   └── occlusion/
│       └── index.html          # Occlusion HTML viewer
└── images/                      # Viewer-ready input images
    ├── backgrounds/
    └── products/
```

## Usage

### 1. Input Images

This package includes viewer-ready input images in `images/backgrounds/` and `images/products/` for direct browsing. Source URLs are still preserved in `dataset_metadata.json` for attribution and traceability. Entries with `status: "generated"` have no source URL and are marked accordingly.

The `stitch_entries` and `occlusion_entries` arrays in `dataset_metadata.json` are stored in the same packaged order used by the supplementary PDFs and HTML viewers. The `id` field matches the sequential example number and the on-disk folder name under `masks/` and `results/`.

### 2. Load Dataset

```python
import json

# Load metadata
with open('dataset_metadata.json', 'r') as f:
    dataset = json.load(f)

for entry in dataset['stitch_entries']:
    print(f"Stitch example {entry['id']}:")
    print(f"  Background: {entry['background']['url']}")
    print(f"  Product: {entry['product']['url']}")

for entry in dataset['occlusion_entries']:
    print(f"Occlusion example {entry['id']}:")
    print(f"  Background: {entry['background']['url']}")
    print(f"  Product: {entry['product']['url']}")
```

### 3. Browse HTML Viewers

Open `index.html` in this folder to access the interactive viewers. Inputs, masks, and model outputs are bundled and render directly in the browser.

## Image Sources & Licensing

Images are sourced from:

| Source | License | Link |
|--------|---------|------|
| Unsplash | [Unsplash License](https://unsplash.com/license) | Free to use, attribution appreciated |
| Pixabay | [Pixabay License](https://pixabay.com/service/license/) | Free for commercial use |
| Pexels | [Pexels License](https://www.pexels.com/license/) | Free to use, attribution appreciated |

**Note:** Some pairs may use AI-generated images (marked in metadata). These are included for completeness but users should verify licensing for their use case.

## What We Provide (Our Contribution)

- **Masks:** Pre-computed segmentation masks (freeform, bounding box, dimension-aware)
- **Annotations:** Aspect ratio measurements, occlusion labels, category tags
- **Metadata:** Source URLs, photographer credits, licensing info
- **Viewers:** HTML pages for quickly browsing the packaged masks and results

## Citation

If you use this dataset, please cite:

```bibtex
@inproceedings{catalogstitch,
  title     = {CatalogStitch: Dimension-Aware and Occlusion-Preserving Object Compositing for Catalog Image Generation},
  author    = {Sanyam Jain and Pragya Kandari and Manit Singhal and He Zhang and Soo Ye Kim},
  booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
  workshop  = {HiGen: Human-Interactive Generation and Editing},
  year      = {2026}
}
```

## Contact

For questions about the dataset, please contact:

- Sanyam Jain — sanyjain@adobe.com
- Pragya Kandari — pkandari@adobe.com
- Manit Singhal — manits@adobe.com
- He Zhang — hezhan@adobe.com
- Soo Ye Kim — sooyek@adobe.com
