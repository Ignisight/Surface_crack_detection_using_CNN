# Surface Crack Detection using CNN

This project builds a deep learning model using **Convolutional Neural Networks (CNN)** to automatically detect cracks on surfaces (concrete, walls, roads, etc.) from images. The goal is to provide a fast, accurate, and scalable tool for structural health monitoring, infrastructure inspection, and preventive maintenance.

## 🧩 Problem Statement
Manual inspection of cracks in buildings, bridges, roads, and industrial structures is time-consuming, costly, and prone to human error. Early and reliable crack detection is essential to prevent structural failures and ensure safety.

This project solves the problem by automating crack detection using a CNN-based binary image classifier — identifying whether a surface has a crack or not, with high confidence and visual localization.

## 📂 Dataset Description
- Dataset: **Surface Crack Detection** from Kaggle (arunrk7/surface-crack-detection)
- Contains thousands of RGB images divided into two classes:
  - **Positive**: Images with visible cracks
  - **Negative**: Images without cracks
- Images are resized to 150×150 pixels during preprocessing
- Data is augmented (shear, zoom, flip) for better generalization
- Split: 80% training / 20% validation (using `validation_split`)
- Final evaluation performed on sample positive & negative images + custom uploaded images

## 🧠 Model: CNN-Based Binary Classifier
A custom **Convolutional Neural Network** built with TensorFlow/Keras:

- **Architecture**:
  - 3 Convolutional blocks (32 → 64 → 128 filters) with ReLU activation
  - MaxPooling layers after each conv block
  - Flatten → Dense (64 units, ReLU) → Dropout (0.5) → Dense (1 unit, Sigmoid)
- **Loss**: Binary Crossentropy
- **Optimizer**: Adam
- **Metrics**: Accuracy
- **Callbacks**: EarlyStopping (patience=3), ModelCheckpoint (save best model)

The model learns to distinguish crack patterns (lines, discontinuities) from normal surface textures.

## 🧪 Results
- Achieved **~99% overall accuracy** on validation data
- **98% correct detection** on cracked (Positive) images
- **100% correct classification** on non-cracked (Negative) images
- Successfully predicts on new/unseen images with high confidence
- Uses **Grad-CAM** to generate heatmaps and draw **green bounding boxes** around detected crack regions for visual explanation

## 🚀 Conclusion & Application
This CNN-based crack detection system can be integrated into:

- 📱 Mobile apps for on-site inspection by engineers & maintenance teams
- 🏗️ Drones & robotic systems for automated infrastructure scanning
- 🏭 Industrial quality control and predictive maintenance platforms
- 🌉 Bridge, dam, and building structural health monitoring tools

Early crack detection helps prevent costly repairs, enhance safety, and extend the lifespan of structures.

## 📌 Technologies Used
- Python
- TensorFlow / Keras
- NumPy, Matplotlib, PIL (Pillow)
- OpenCV (for visualization)
- Google Colab (development environment)
- Kaggle API (dataset download)
- Grad-CAM (for explainability & bounding box)

## How to Run
1. Open in Google Colab
2. Replace Kaggle username & API key in the setup section
3. Run all cells sequentially
4. Upload your own surface image at the end to test detection + visualization

Feel free to fork, contribute, or use this project for academic, research, or industrial applications!

⭐ If you find this helpful, give it a star!
