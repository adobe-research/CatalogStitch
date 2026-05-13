# CatalogStitch

**CatalogStitch: Dimension-Aware and Occlusion-Preserving Object Compositing for Catalog Image Generation**

[Sanyam Jain](https://www.linkedin.com/in/jainsanyam/), [Pragya Kandari](https://www.linkedin.com/in/pragya-k-8083133a/), [Manit Singhal](https://www.linkedin.com/in/manit-singhal-260162216/), [He Zhang](https://sites.google.com/site/hezhangsprinter), [Soo Ye Kim](https://sites.google.com/view/sooyekim)

**Adobe**

**CVPR 2026 — HiGen Workshop (Human-Interactive Generation and Editing)**

[[Project Page](https://catalogstitch.github.io)] [[Paper](https://catalogstitch.github.io/CatalogStitch.pdf)] [[arXiv](https://arxiv.org/abs/2604.08836)]

---

## License

This dataset is released under the [Adobe Research License](dataset/LICENSE.md) for noncommercial research purposes only. See [`dataset/LICENSE.md`](dataset/LICENSE.md) for the full license text and third-party image licensing details.

---

## CatalogStitch-Eval Benchmark

A 58-example evaluation benchmark for catalog image compositing:

- **35 dimension-mismatch scenes** — products with significantly different aspect ratios
- **23 occlusion scenes** — products partially occluded by 1–2 foreground elements

### Contents

| Component | Path | Description |
|---|---|---|
| Background images | `dataset/images/backgrounds/` | High-resolution scene images with target product regions |
| Product images | `dataset/images/products/` | Replacement product images for compositing |
| Masks | `dataset/masks/` | Freeform, bounding box, and dimension-aware masks per example |
| Model outputs | `dataset/results/` | Composited outputs from ObjectStitch, OmniPaint, and InsertAnything |
| Metadata | `dataset/dataset_metadata.json` | Source URLs, licensing information, and quantitative metrics |
| PDF summaries | `additional_results_*.pdf` | Full visual results for all 58 benchmark examples |
| Interactive viewers | `dataset/results/*/index.html` | Side-by-side comparison browsers |

### Interactive Viewers

- [Dataset Overview](dataset/index.html)
- [Dimension-Aware Results (35 examples)](dataset/results/stitch/index.html)
- [Occlusion Restoration Results (23 examples)](dataset/results/occlusion/index.html)

---

## Citation

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

- Sanyam Jain — sanyjain@adobe.com
- Pragya Kandari — pkandari@adobe.com
- Manit Singhal — manits@adobe.com
- He Zhang — hezhan@adobe.com
- Soo Ye Kim — sooyek@adobe.com
