# Balanced Multiclass Synthetic BreakHis (Aug + cDCGAN)

This dataset provides a **balanced** version of BreakHis across **8 subtypes**:
Adenosis, Fibroadenoma, Phyllodes, Tubular, Ductal, Lobular, Mucinous, Papillary.
It includes images generated via **Albumentations** and a **conditional DCGAN** to diminish class disparity.

## Source
- Original images: BreakHis (10.17632/jxwvdwhpc2.1).
- Synthetic methods: Albumentations (augmentation), conditional DCGAN (PyTorch).

## Metadata
- See `metadata.csv` with columns:
  - filename, subtype, magnif, source (aug|gan), method (albumentations|cDCGAN|albumentations-extra)

## Generation Details
- Augmentation:
  - Strong on rare subtypes (ShiftScaleRotate, ColorJitter, Noise, CLAHE, etc.)
  - Light on common subtypes.
- GAN:
  - Conditional DCGAN per subtype, GAN_IMG_SIZE={cfg.GAN_IMG_SIZE}, EPOCHS={cfg.GAN_EPOCHS}.
  - SSIM filtering against real references; threshold={cfg.SSIM_THRESHOLD}.

## Intended Use
- Benchmarking **multiclass breast histopathology classification**.
- Research on **class imbalance** mitigation and **synthetic data** in pathology.

## Citation
- BreakHis: cite the original dataset publication.
- If you publish using this dataset, please cite using the DOI of this paper.

