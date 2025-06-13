
# 🌿 Multimodal Plant Leaf Disease Detection

This repository contains a robust pipeline for detecting plant leaf diseases using image data captured under **multiple light sources** and **UV conditions**. The project leverages both **deep learning** and **machine learning** models to explore and compare performance across different light modalities.

---

## 🧪 Project Summary

The goal of this work is to classify **healthy** vs **unhealthy** leaves based on image features extracted under the following lighting modalities:

### ✅ Light Modalities Used:
- **365nm NoUV**
- **365nm UV**
- **395nm NoUV**
- **395nm UV**
- **White Light NoUV**
- **White Light UV**

Each of these modalities captures unique reflectance and fluorescence characteristics that can help in identifying disease symptoms more effectively.

---

## 🧠 Models Utilized

### 🔸 Deep Learning Models:
- **Vision Transformer (ViT)**
- **VGG16 (Pretrained)**
- **ResNet-18** (Custom backbones)

> For ResNet-18, two configurations were used:
- **3-backbone mode**: One model per modality group (NoUV, UV, UV+NoUV)
- **6-backbone mode**: One model for each specific modality (all 6 folders)

### 🔸 Machine Learning Models (on extracted embeddings):
- **Support Vector Machine (SVM)**
- **XGBoost**
- **Random Forest**

Embeddings from ViT, VGG16, and ResNet18 were used as input features to train these classifiers for binary classification.

---

## 📊 Modalities vs Performance

Using t-SNE and other dimensionality reduction techniques, we visualized the **distribution of embeddings** to evaluate how well healthy and unhealthy samples are separated across modalities.

Key observations:
- **WhiteUV** and **365NoUV** showed the most **distinct and compact clusters**.
- **UV modalities** (especially 365UV and 395UV) had **higher noise and overlap** between classes.
- **Combined UV+NoUV** backbones improved performance by learning complementary features.

---

## 📁 Folder Structure (Expected)
```
├── embeddings/                 # Extracted .npy files for each modality
├── models/                    # Trained DL/ML model files
├── plots/                     # t-SNE, UMAP, and performance graphs
├── Leaf Dataset/
│   ├── 365NoUV/
│   ├── 365UV/
│   ├── ...
│   └── labels.csv             # Ground truth (filename,label)
├── notebooks/
│   └── experiments.ipynb      # Training & evaluation scripts
├── README.md
└── requirements.txt
```

---

## 📈 Visual Analysis Tools

We used both **2D and 3D t-SNE/UMAP plots** to visualize the embeddings generated from each model. These plots help in understanding:
- Cluster separation
- Feature richness
- Overlap between healthy/unhealthy samples

---


## ✅ Key Results

| Model        | UV Accuracy | NoUV Accuracy  | Combined Accuracy | Best Feature               |
|--------------|-------------|----------------|-------------------|----------------------------|
| ViT          | 60.82%      | 80.71%         | 70.61%            | NoUV(RGB)                  |
| VGG16        | 83.07%      | 86.5%          | 87.76%            | UV+RGB(Combined)           |
| ResNet18 (6) | 86.2%       | 87.56%         | 88.73%            | UV+RGB(Combined)           |
| XGBoost      | 79.3%       | 81.49%         | 81.14%            | UV+RGB(Combined) alsmost   |
| SVM          | 80.45%      | 81.82%         | 82.17             | UV+RGB(Combined)           |



---

## 🔧 Installation & Usage

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/plant-disease-multimodal.git
   cd plant-disease-multimodal
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:
   ```bash
   jupyter notebook notebooks/experiments.ipynb
   ```

---

## 🔍 Future Work
- Fine-tuning ViT models on each modality individually.
- Integrating early/late fusion strategies for ResNet backbones.
- Extending the framework to multiclass disease classification.
- Real-time deployment on edge devices with optimized UV+RGB cameras.

---

## 👨‍🔬 About the Author

This project was developed by **Deepak Kumar**, a B.Tech (Hons.) Data Science student at CSVTU Bhilai, as part of his research internship under the guidance of [Prof. Tushar Sandhan](https://home.iitk.ac.in/~tushars/) at the **Electrical Engineering Department, IIT Kanpur**.  
The work contributes to ongoing research focused on building robust and scalable plant disease detection systems using multimodal imaging techniques.

---

## 📫 Contact  
If you have questions or suggestions, feel free to reach out:

- 📧 Email: deepak0778671@gmail.com
- 🌐 LinkedIn: [Deepak Kumar](www.linkedin.com/in/deepak-kumar-029781263)
- 🧠 HuggingFace: [PotatoSage](https://huggingface.co/spaces/Deepakkumar5570/PotatoSage)

---

## 📄 License
This project is licensed under the **MIT License**. See the `LICENSE` file for details.
