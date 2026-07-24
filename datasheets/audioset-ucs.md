# Datasheet: AudioSet-UCS

UCS-mapped re-labeling of the AudioSet balanced subset. Follows the datasheet framework of Gebru et al. [1].
This repository distributes **CSV metadata only** — audio must be obtained from the original source.

- **Data repository:** https://github.com/JunWooBeck/audioset-ucs
- **Conversion pipeline:** https://github.com/JunWooBeck/ucs-sfx-tools
- **UCS version:** 8.2.1

## Motivation

- **Purpose:** Large-scale human-labeled audio event dataset [2]; balanced subset re-labeled to UCS.
- **Creators:** Gemmeke et al. (Google Research). UCS re-labeling by the authors of [3].

## Composition

- 32,767 classified files (17,176 balanced_train + 15,591 eval) plus 501 unclassified (1.51%), 60 UCS categories
- 10-second clips from YouTube; multi-label AudioSet tags re-mapped to a single UCS Category/SubCategory
- Unbalanced training set (~2M clips) excluded due to computational constraints
- 70/15/15 stratified splits (seed 42)
- 9,160 files flagged for ambiguity review; original labels contain crowd-sourced noise

## Collection

- Audio from YouTube (Google Research); human-annotated with the AudioSet ontology
- UCS conversion pipeline: pre-defined mapping → SubCategory match → Category match → synonym lookup → conflict resolution

## Uses & Limitations

- Used as a UCS-relabeled benchmark for flat and hierarchical classification
- **Not suitable as ground truth for UCS taxonomy evaluation**; original AudioSet labels contain annotation noise
- Note for benchmarking: PANNs CNN14 embeddings [4] were pretrained on the full AudioSet corpus, so roughly 51% of this subset's test files were seen during that pretraining

## Distribution & License

- UCS labels and splits: https://github.com/JunWooBeck/audioset-ucs — audio from the AudioSet website (YouTube Terms of Service apply; audio cannot be redistributed)
- AudioSet annotations: CC-BY 4.0; ontology: CC-BY-SA 4.0. Our metadata: CC-BY-SA 4.0
- Maintained by the authors

## References

1. T. Gebru, J. Morgenstern, B. Vecchione, J. W. Vaughan, H. Wallach, H. Daumé III, and K. Crawford, "Datasheets for Datasets," *Communications of the ACM*, vol. 64, no. 12, pp. 86–92, Dec. 2021.
2. J. F. Gemmeke, D. P. W. Ellis, D. Freedman, A. Jansen, W. Lawrence, R. C. Moore, M. Plakal, and M. Ritter, "Audio Set: An Ontology and Human-Labeled Dataset for Audio Events," in *Proc. IEEE ICASSP*, New Orleans, LA, 2017, pp. 776–780.
3. J. W. Beck and A. Lerch, "Sound Effects Dataset Unification With the Universal Category System," in *Proc. Int. Conf. Digital Audio Effects (DAFx)*, Cambridge, MA, USA, 2026.
4. Q. Kong, Y. Cao, T. Iqbal, Y. Wang, W. Wang, and M. D. Plumbley, "PANNs: Large-Scale Pretrained Audio Neural Networks for Audio Pattern Recognition," *IEEE/ACM Trans. Audio, Speech, and Language Processing*, vol. 28, pp. 2880–2894, 2020.
