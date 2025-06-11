# Violence Detection Dataset for Computer Vision Research

## 📋 Dataset Overview

**Dataset for Confidence-Based Segmentation in Violence Detection Using DenseNet121**

This dataset supports the research presented in: *"Análisis de la Ambigüedad en Imágenes de Violencia y No Violencia mediante Subconjuntos de Muestra Safe, Border y Average con DenseNet121"*

### 🎯 Research Context

Violence detection in multimedia content represents a critical challenge in the digital era, where millions of images are shared daily across platforms. This dataset was specifically curated to address the inherent ambiguity in violence/non-violence classification by introducing **confidence-based segmentation methodology** that transforms uncertainty into specialized optimization opportunities.

## 📊 Dataset Composition

### Core Dataset Structure:
- **Base Training Set:** 6,000 images (perfectly balanced)
  - Violence: 3,000 images
  - Non-Violence: 3,000 images
- **Consistent Test Set:** 4,420 images (used across all experiments)
  - Violence: 2,200 images  
  - Non-Violence: 2,220 images
- **Extended Training Set:** 11,600 images (for global comparison)
  - Violence: 5,800 images
  - Non-Violence: 5,800 images

### 🔬 Experimental Methodology

Our innovative approach consists of multiple phases:

1. **Base Model Training:** DenseNet121 trained with 6,000 balanced images
2. **Confidence Analysis:** Extract prediction confidence on test set (4,420 images)
3. **Intelligent Segmentation:** Classify training images into Safe/Border/Average subsets
4. **Specialized Training:** Train dedicated models for each subset
5. **Consistent Evaluation:** All models tested on the same 4,420 test images
6. **Global Comparison:** Compare against DenseNet121 trained with 11,600 images

## 🧠 Confidence-Based Segmentation Innovation

### The Revolutionary Process:

After training the base DenseNet121 model, we analyze its confidence levels on predictions and strategically segment the training data into three specialized subsets:

### 📊 Safe Subset (High Confidence Cases)
- **Extraction Criteria:** Images where base model shows confidence ≥0.9 or ≤0.1
- **Characteristics:** Unambiguous cases with clear visual patterns
- **Training Purpose:** Maximize precision for critical applications
- **Typical Size:** ~10,600-11,000 images

### ⚖️ Border Subset (Ambiguous Cases)  
- **Extraction Criteria:** Images where base model shows confidence 0.4-0.6
- **Characteristics:** Inherently challenging cases requiring specialized handling
- **Training Purpose:** Robust performance under uncertainty
- **Typical Size:** ~6,100-6,200 images

### 📈 Average Subset (Representative Cases)
- **Extraction Criteria:** Images with confidence μ±σ (adaptive based on distribution)
- **Characteristics:** Typical difficulty range for real-world scenarios
- **Training Purpose:** Optimized general-purpose performance
- **Typical Size:** ~7,100-9,800 images

## 🎯 Evaluation Strategy

### Consistent Testing Protocol:
**ALL models are evaluated on the SAME test set:**
- Violence: 2,200 images
- Non-Violence: 2,220 images
- Total: 4,420 test images (completely independent from training)

This ensures fair comparison and eliminates test set bias across different model configurations.

## 🚀 Breakthrough Results Achieved

### Performance Improvements vs Base Model (6K training):
- **Average Subset Model:** 87.3% F1-Score (**+13.5% improvement**)
- **Safe Subset Model:** 98.8% Precision (**94% reduction in false positives**)  
- **Border Subset Model:** 80.6% F1-Score (**+4.8% improvement** in difficult cases)

### Comparison with Global Model (11.6K training):
- **DenseNet Global:** 99.0% across all metrics (theoretical upper limit)
- **Efficiency Analysis:** Specialized models achieve excellent performance with fewer resources

## 🔬 Scientific Innovation

### Why This Methodology is Revolutionary:

1. **Confidence as Strategy:** First systematic use of prediction confidence for training segmentation
2. **Ambiguity Advantage:** Transforms classification uncertainty into optimization opportunity
3. **Specialized Excellence:** Different models optimized for different difficulty levels
4. **Resource Efficiency:** Better performance with targeted training vs. brute force scaling
5. **Practical Applications:** Hierarchical deployment based on confidence requirements

## 📁 Dataset Structure
