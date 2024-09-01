![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

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
### New cif (perovskite only)
- Mix halide I->Br, manual generation cif, linear in between, step 10% composition
- FA/Cs/MA, Pb/Sn, Cl/Br/I

### Preprocessing
- Setting: 5-60, 2 theta, step size: 0.01, interpolation
- Lattice 0.95-1.05 factor (a,b,c?)
- Missing peak

### Label
- Element (EDS) or precursor label: MA Cs Pb Br (text input)
- Space group label: 64 (output)
- Chemical formula: gamma-CsPbI3 (human)

### Dataloader
- Random peak intensity 
- Random crystal size
- Random mixing ratio

## Evaluation
- Output: class label + probability (multi-label classification) -> natural language description
- Train valid test: 60:20:20
- Top5 accuracy (precision recall F1)
- Confusion matrix

- Compare: No text prior / Wrong text prior

## Extra things to do
Various data range
