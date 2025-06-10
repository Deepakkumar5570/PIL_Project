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



---

## 📊 Modalities vs Performance

Using t-SNE and other dimensionality reduction techniques, we visualized the **distribution of embeddings** to evaluate how well healthy and unhealthy samples are separated across modalities.

Key observations:
- **WhiteUV** and **365NoUV** showed the most **distinct and compact clusters**.
- **UV modalities** (especially 365UV and 395UV) had **higher noise and overlap** between classes.
- **Combined UV+NoUV** backbones improved performance by learning complementary features.

---

## 📁 Folder Structure (Expected)









## 👨‍🔬 About the Author
This project was developed by Deepak Kumar, a B.Tech (Hons.) Data Science student at CSVTU Bhilai, as part of his research internship under the guidance of Prof. Tushar Sandhan at the Electrical Engineering Department, IIT Kanpur.
The work contributes to ongoing research focused on building robust and scalable plant disease detection systems using multimodal imaging techniques.

📫 Contact
If you have questions or suggestions, feel free to reach out:

📧 Email: deepak0778671@gmail.com

🌐 LinkedIn: Deepak Kumar

