# Datasheet: FSD50K-UCS

UCS-mapped re-labeling of FSD50K. Follows the datasheet framework of Gebru et al. [1].
This repository distributes **CSV metadata only** — audio must be obtained from the original source.

- **Data repository:** https://github.com/JunWooBeck/fsd50k-ucs
- **Conversion pipeline:** https://github.com/JunWooBeck/ucs-sfx-tools
- **UCS version:** 8.2.1

## Motivation

- **Purpose:** Large-scale open dataset of human-labeled sound events [2], re-labeled to the Universal Category System (UCS).
- **Creators:** Fonseca et al. (Music Technology Group, Universitat Pompeu Fabra). UCS re-labeling by the authors of [3].

## Composition

- 51,197 classified files (40,966 dev + 10,231 eval), 100% classification rate, 37 UCS categories
- Variable-length audio clips (0.3–30 s) from Freesound, re-mapped to UCS Category and SubCategory
- Single UCS Category/SubCategory per file; original FSD50K tags retained
- 70/15/15 stratified splits (seed 42)
- 8,086 files flagged for ambiguity review; ties resolved deterministically without auditory verification

## Collection

- Audio from Freesound.org (Creative Commons licensed); labels via automated retrieval + human validation
- UCS labels derived algorithmically via the conversion pipeline

## Uses & Limitations

- Used as a UCS-relabeled benchmark for flat and hierarchical classification
- UCS labels are algorithmically derived and **should not be treated as verified ground truth**

## Distribution & License

- UCS labels and splits: https://github.com/JunWooBeck/fsd50k-ucs — audio from Zenodo
- Audio: Creative Commons (varies per clip). Metadata: CC-BY-SA 4.0
- Maintained by the authors; updates follow UCS revisions

## References

1. T. Gebru, J. Morgenstern, B. Vecchione, J. W. Vaughan, H. Wallach, H. Daumé III, and K. Crawford, "Datasheets for Datasets," *Communications of the ACM*, vol. 64, no. 12, pp. 86–92, Dec. 2021.
2. E. Fonseca, X. Favory, J. Pons, F. Font, and X. Serra, "FSD50K: An Open Dataset of Human-Labeled Sound Events," *IEEE/ACM Trans. Audio, Speech, and Language Processing*, vol. 30, pp. 829–852, 2022.
3. J. W. Beck and A. Lerch, "Sound Effects Dataset Unification With the Universal Category System," in *Proc. Int. Conf. Digital Audio Effects (DAFx)*, Cambridge, MA, USA, 2026.
