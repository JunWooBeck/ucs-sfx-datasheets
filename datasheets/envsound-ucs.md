# Datasheet: EnvSound-UCS

Combined environmental sound benchmark assembled from ESC-50, FSD50K, and AudioSet under UCS.
Follows the datasheet framework of Gebru et al. [1].
This repository distributes **CSV metadata only** — audio must be obtained from the three original sources.

- **Data repository:** https://github.com/JunWooBeck/envsound-ucs
- **Conversion pipeline:** https://github.com/JunWooBeck/ucs-sfx-tools
- **UCS version:** 8.2.1

## Motivation

- **Purpose:** Provide consistent multi-source data for research on SFX classification and generation under a single label space.
- **Creators:** The authors of [2].

## Composition

- 58,057 samples across 59 UCS categories (`MUSICAL` excluded; `VOICES` restricted to `CRYING`/`LAUGH`)
- Union of all UCS-classified files from the three sources that map to the retained categories
- Per-source contribution: 33,065 from FSD50K, 22,992 from AudioSet, 2,000 from ESC-50 (from a combined pool of 85,964 files)
- Per instance: UCS Category, SubCategory, original keywords, source provenance (CSV metadata only)
- Split-then-merge: each source split 70/15/15 independently (seed 42), then concatenated
- Inherits noise from all sources; cross-source label inconsistencies are possible by design

## Collection

- No new audio collected; assembled via `combine_and_split.py` (load CSVs → filter categories → verify files → stratified split)

## Uses & Limitations

- Combined benchmark reference results: flat subcategory classifier macro F1 = 0.49; hierarchical with oracle routing = 0.73
- **Not suitable for evaluating UCS taxonomy quality**; account for source-level differences when comparing
- Category coverage is uneven: 33 of the 59 categories have no ESC-50 representation

## Distribution & License

- Configuration and split CSVs: https://github.com/JunWooBeck/envsound-ucs — audio from the original sources
- Audio licenses, most restrictive terms apply: AudioSet (YouTube Terms of Service, no redistribution), FSD50K (Creative Commons, varies per clip), ESC-50 (CC-BY-NC 3.0, **non-commercial**)
- Our metadata: CC-BY-SA 4.0
- Maintained by the authors; version-controlled for future source additions and UCS revisions

## References

1. T. Gebru, J. Morgenstern, B. Vecchione, J. W. Vaughan, H. Wallach, H. Daumé III, and K. Crawford, "Datasheets for Datasets," *Communications of the ACM*, vol. 64, no. 12, pp. 86–92, Dec. 2021.
2. J. W. Beck and A. Lerch, "Sound Effects Dataset Unification With the Universal Category System," in *Proc. Int. Conf. Digital Audio Effects (DAFx)*, Cambridge, MA, USA, 2026.
