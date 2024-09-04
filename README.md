![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

# XRD-ViT-Chem

### Dependency
- Python	3.8.18 (KJ) / 3.11.8 (FS)
- Pytorch 1.13.1 (KJ)
- numpy	1.24.3 (KJ,FS)
- xrayutilities	1.7.4 (KJ) / 1.7.8 (FS)
- pymatgen	2023.8.10 (KJ)

## Goal
- Natural language (text embedding) + XRD raw data (XRD embedding)
- Text embedding -> elements/expected compound (input prior), sparse coding
- XRD embedding -> 1d or 2d (nx1) embedding, continuous

## Dataset
### New cif for mix A/B/X perovskite
- [x] Data collection (Cs/FA/MA, Pb/Sn, Cl/Br/I)
- [x] Combination search
- [x] Mixed cif generation, step size 10% across composition gradient

### Preprocess
- [x] Lattice strain between -0.02~+0.02 for a, b, c; Step size 0.01
- [x] Label 1 - Element (EDS) and precursor label: MA Cs Pb Br (text input)
- [x] Label 2 - Space group label: 64 (output)
- [x] Label 3 - Chemical formula: gamma-CsPbI3 (human)
- [x] Dataset creation (save/load) for i) new cif and ii) ICSD

### Impurity and substrate study
- [ ] Data collection: target material, potential impurities or substrates, corresponding ICSD for all materials, references

### Dataloader
- [x] Expand from nonzero to full range XRD
- [x] Missing peak
- [x] Random peak intensity
- [x] Random crystal size
- [x] Mixing of compounds, with random ratio
- [x] Add background noise

## Training

## Evaluation
- [ ] Output: class label + probability (multi-label classification) -> natural language description
- [ ] Top5 accuracy (precision recall F1)
- [ ] Confusion matrix

- [ ] Compare: No text prior / Wrong text prior

## Extra / bonus
- [ ] Various data range
