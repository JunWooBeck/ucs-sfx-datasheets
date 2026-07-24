# Datasheet: ESC-50-UCS

UCS-mapped re-labeling of ESC-50. Follows the datasheet framework of Gebru et al. [1].
This repository distributes **CSV metadata only** — audio must be obtained from the original source.

- **Data repository:** https://github.com/JunWooBeck/esc50-ucs
- **Conversion pipeline:** https://github.com/JunWooBeck/ucs-sfx-tools
- **UCS version:** 8.2.1

## Motivation

- **Purpose:** Environmental sound classification benchmark [2], re-labeled to UCS.
- **Creators:** Karol J. Piczak. UCS re-labeling by the authors of [3].

## Composition

- 2,000 clips, 50 classes, 5 major categories, 40 clips/class, 26 UCS categories
- 5-second WAV files at 44.1 kHz from Freesound.org; single categorical label plus derived UCS Category
- Original 5-fold CV available; a 70/15/15 stratified split is applied for the EnvSound-UCS study
- Curated dataset with clean labels; UCS mapping is straightforward (100% classification rate, no ambiguity flags)

## Collection

- Manually selected from Freesound.org; all clips Creative Commons licensed

## Uses & Limitations

- Standalone benchmark and source dataset for EnvSound-UCS
- Limited scope (50 classes, 2,000 clips); not suitable for comprehensive general-purpose evaluation

## Distribution & License

- ESC-50 audio: https://github.com/karolpiczak/ESC-50 under CC-BY-NC 3.0 (**non-commercial**)
- UCS mappings: https://github.com/JunWooBeck/esc50-ucs. Our metadata: CC-BY-SA 4.0
- Maintained by Piczak (original) and the authors (UCS mappings)

## References

1. T. Gebru, J. Morgenstern, B. Vecchione, J. W. Vaughan, H. Wallach, H. Daumé III, and K. Crawford, "Datasheets for Datasets," *Communications of the ACM*, vol. 64, no. 12, pp. 86–92, Dec. 2021.
2. K. J. Piczak, "ESC: Dataset for Environmental Sound Classification," in *Proc. ACM Int. Conf. Multimedia*, Brisbane, Australia, 2015, pp. 1015–1018.
3. J. W. Beck and A. Lerch, "Sound Effects Dataset Unification With the Universal Category System," in *Proc. Int. Conf. Digital Audio Effects (DAFx)*, Cambridge, MA, USA, 2026.
