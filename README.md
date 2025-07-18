# MUPPET (*M*edNeXt *U*nimodal *P*erivascular s*P*ace *E*xtractor *T*ool)
Pretrained models for automated 3D perivascular space (PVS) segmentation in T1- and T2-weighted MRI.
- **T2w models (MedNeXt, nnUNet):**
  + trained on 200 T2w MRIs (HCP Aging)
  + segment white matter PVS only
- **T1w model (MedNeXt):**
  + trained on 40 T1w MRIs from a heterogeneous dataset (mild cognitive impairment, dementia, and healthy controls)
  + segments PVS in white matter and basal ganglia

# Installation
The repository can be cloned and installed using the following commands.
```
git clone https://github.com/iBRAIN-Lab/MUPPET.git muppet
cd muppet
conda env create -f MUPPET_env.yml
conda activate MUPPET_env
```

# Pretrained Weights
Download pretrained weights from the [Releases](https://bridges.monash.edu/articles/dataset/PINGU_Weights/27176523?file=49632888) page.

Pretrained weights are organized by model and fold. Each folder contains the best checkpoint from that fold’s training run:
```
weights/
├── T2w_nnunet/
│   └── fold_0/
│       └── debug.json
│       └── model_best.model
│       └── model_best.model.pkl
│   ... (folds 1-4)
│ 
├── T2w_mednext/
│   └── fold_0/
│       └── debug.json
│       └── model_best.model
│       └── model_best.model.pkl
│   ... (folds 1-4)
│ 
├── T1w_mednext/
│   └── fold_0/
│       └── debug.json
│       └── model_best.model
│       └── model_best.model.pkl
│   ... (folds 1-4)
│ 
```

# Inference Usage
Place your T1w/T2w NIfTI images (named *_0000.nii.gz) in a single input folder.
