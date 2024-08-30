# XRD-ViT-Chem

### Dependency

- Python	3.8.18 (KJ) / 3.11.8 (FS)

- Pytorch 1.13.1 (KJ)

- numpy	1.24.3 (KJ,FS)

- xrayutilities	1.7.4 (KJ) / 1.7.8 (FS)

- pymatgen	2023.8.10 (KJ)

## Goal
- natural language (text embedding) + XRD raw data (XRD embedding)
- Text embedding -> elements/expected compound (input prior), sparse coding
- XRD embedding -> 1d or 2d (nx1) embedding, continuous

## Dataset
- Basic dataset: download standard XRD patterns from the dataset (FA/MA/Cs, Pb, I/Br/Cl gradient), impurity (delta phase, PbI2, CsI)
- Preprocessing: 5-60, 2 theta, step size: 0.01, interpolation
- Mixed phase dataset: change peak intensity, ratio between different phases (generated), peak shift (halide difference), peak broadening, error generation -> generate large dataset with multiple phases

- Corresponding text data: possible cations/anions

- Output: class label + probability (multi-label classification) -> natural language description

- Train valid test: 60:20:20

## Evaluation
- Top5 accuracy (precision recall F1)
- Confusion matrix

- Compare: No text prior / Wrong text prior

## Extra things to do
Various data range
