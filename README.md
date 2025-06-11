# Violence Detection Dataset - Confidence-Based Segmentation

## 📋 Overview

Dataset for research on **confidence-based segmentation** in violence detection using DenseNet121. Transforms classification ambiguity into specialized training opportunities.

## 📥 Downloads

### Base Dataset (DenseNet121 Pre-training)
**[Download Base Dataset](https://drive.google.com/file/d/1Mvbi5xPrcvEexSQqAgZK3vrx9ugxsJHk/view?usp=drive_link)**
- Training/validation images with standard splits
- Test set: 2,200 violence + 2,220 non-violence images

### Complete Research Dataset  
**[Download Full Dataset](https://drive.google.com/file/d/1_DBKm9edOJLhIKFH2GWW_6hOGh5mBSdP/view?usp=drive_link)**
- dataset1: 6K balanced training images (3K violence + 3K non-violence)
- dataset2: Extended collection for subset extraction
- Same test set for consistent evaluation

## 📊 Dataset Structure
violence-detection-research/
├── base-violence-dataset/           # From first download link
│   ├── dataset/
│   │   ├── train/
│   │   │   ├── violence/           # Base training violence images
│   │   │   └── non_violence/       # Base training non-violence images
│   │   └── validation/
│   │       ├── violence/           # Validation violence images
│   │       └── non_violence/       # Validation non-violence images
│   └── test/
│       ├── violence/               # 2,200 test violence images
│       └── non_violence/           # 2,220 test non-violence images
├── confidence-segmentation-dataset/ # From second download link
│   ├── dataset/
│   │   ├── dataset1/               # Base model training (6K)
│   │   │   ├── violence/           # 3,000 violence images
│   │   │   └── non_violence/       # 3,000 non-violence images
│   │   └── dataset2/               # Extended for subset extraction
│   │       ├── violence/           # Extended violence collection
│   │       └── non_violence/       # Extended non-violence collection
│   └── test/                       # Consistent evaluation set
│       ├── violence/               # 2,200 test violence images
│       └── non_violence/           # 2,220 test non-violence images
└── generated_subsets/              # Created during confidence segmentation
    ├── safe/                       # High confidence training cases
    ├── border/                     # Ambiguous training cases
    └── average/                    # Representative training cases

## 🧠 Methodology

1. **Train base model** with dataset1 (6K images)
2. **Extract confidence scores** on test predictions  
3. **Segment dataset2** into Safe/Border/Average subsets
4. **Train specialized models** for each subset
5. **Evaluate all models** on same test set (4,420 images)

### Confidence Subsets:
- **Safe:** Confidence ≥0.9 or ≤0.1 (unambiguous cases)
- **Border:** Confidence 0.4-0.6 (ambiguous cases)  
- **Average:** Confidence μ±σ (representative cases)

## 🎯 Technical Specs

- **Images:** 224×224 pixels, RGB, ImageNet normalized
- **Balance:** Perfect 1:1 violence/non-violence ratio
- **Quality:** High-resolution, manually verified
- **Format:** JPEG/PNG compatible with PyTorch/TensorFlow

## 🔬 Research Innovation

**First systematic approach** using prediction confidence as training segmentation criterion. Transforms ambiguity from limitation into optimization advantage.

## 📝 Quick Start

```python
# 1. Load base training data (dataset1)
train_data = load_images("dataset/dataset1/")  # 6K images

# 2. Train base model & extract confidence
base_model = train_densenet121(train_data)
confidence_scores = base_model.predict_proba(test_set)

# 3. Generate specialized subsets from dataset2
safe_subset = extract_safe_cases(dataset2, confidence_scores)
border_subset = extract_border_cases(dataset2, confidence_scores)
average_subset = extract_average_cases(dataset2, confidence_scores)

# 4. Train & evaluate specialized models
safe_model = train_densenet121(safe_subset)
results = evaluate_all_models(test_set)



## ⚖️ License & Ethics

- **License**: CC BY 4.0  
- **Purpose**: Academic research only  
- **Content Warning**: Contains violence imagery  
- **Restrictions**: No commercial surveillance, no discriminatory use  

## 📧 Contact

- **Francisco Primero**: [mm23281646@toluca.tecnm.mx](mailto:mm23281646@toluca.tecnm.mx)  
- **Roberto Alejo**: [ralejoe@toluca.tecnm.mx](mailto:ralejoe@toluca.tecnm.mx)  
- **Institution**: Tecnológico Nacional de México / IT Toluca
