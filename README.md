# UCS-SFX Datasheets

Dataset documentation for the four UCS-mapped sound effects datasets introduced in:

> J. W. Beck and A. Lerch, "Sound Effects Dataset Unification With the Universal Category System,"
> in *Proc. Int. Conf. Digital Audio Effects (DAFx)*, Cambridge, MA, USA, 2026.

Each datasheet follows the framework of Gebru et al., *Datasheets for Datasets*
(Communications of the ACM 64(12), 2021), covering motivation, composition, collection,
intended uses and limitations, and distribution and licensing.

## Datasheets

| Dataset | Files | UCS categories | Datasheet | Data repository |
|---|---:|---:|---|---|
| FSD50K-UCS | 51,197 | 37 | [fsd50k-ucs.md](datasheets/fsd50k-ucs.md) | https://github.com/JunWooBeck/fsd50k-ucs |
| AudioSet-UCS | 32,767 | 60 | [audioset-ucs.md](datasheets/audioset-ucs.md) | https://github.com/JunWooBeck/audioset-ucs |
| ESC-50-UCS | 2,000 | 26 | [esc50-ucs.md](datasheets/esc50-ucs.md) | https://github.com/JunWooBeck/esc50-ucs |
| EnvSound-UCS | 58,057 | 59 | [envsound-ucs.md](datasheets/envsound-ucs.md) | https://github.com/JunWooBeck/envsound-ucs |

The conversion pipeline and the UCS-aware re-splitting tool live in
https://github.com/JunWooBeck/ucs-sfx-tools.

## Audio is not distributed here

**These repositories distribute CSV metadata only** — per-file UCS labels, train/validation/test
partitions, and ambiguity review lists. No audio is redistributed for any dataset.
Audio must be obtained from the original sources:

| Dataset | Source | Audio license |
|---|---|---|
| FSD50K | Zenodo / Freesound | Creative Commons, varies per clip |
| AudioSet | AudioSet website (YouTube) | YouTube Terms of Service; no redistribution |
| ESC-50 | https://github.com/karolpiczak/ESC-50 | CC-BY-NC 3.0 (non-commercial) |

Because EnvSound-UCS aggregates all three, anyone assembling the full audio corpus must
respect the **most restrictive** terms that apply — in particular the ESC-50 non-commercial
constraint and the AudioSet redistribution restriction.

## Labels are algorithmically derived

UCS labels in all four datasets are produced by a rule-based tag-matching pipeline without
auditory verification, and they inherit any noise present in the source annotations.
They should not be treated as verified ground truth, and they are not suitable for evaluating
the quality of the UCS taxonomy itself. Files where the conflict-resolution rules were invoked
are recorded in the per-dataset ambiguity review lists.

## Versioning

All datasheets describe the state of the datasets under **UCS v8.2.1**.
Later UCS releases may add, rename, or restructure categories, which would require
re-running the conversion pipeline and updating the affected datasheets.

## License

UCS-SFX Datasheets (c) 2026 by Jun Woo Beck and Alexander Lerch

The metadata and documentation in this repository are licensed under a
Creative Commons Attribution-ShareAlike 4.0 International License.
You should have received a copy of the license along with this work.
If not, see <https://creativecommons.org/licenses/by-sa/4.0/>.

**This license covers the CSV metadata and the datasheets only.** The audio
recordings they describe are not redistributed here and remain under the terms
of their original sources — see the table above. In particular, ESC-50 audio is
CC-BY-NC 3.0 (non-commercial) and AudioSet audio may not be redistributed.
