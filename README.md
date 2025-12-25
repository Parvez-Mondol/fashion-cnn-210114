# fashion-cnn-210114
Machine Learning Assignment 

---

## 🔄 Data Preprocessing
The following preprocessing steps are applied uniformly to **both standard and custom images**:

- Resize to **28 × 28**
- Convert to **grayscale**
- Normalize pixel values using dataset mean & standard deviation
- Convert to PyTorch tensors
- Reshape: `(28, 28)` → `(1, 28, 28)`

Consistent preprocessing is critical for reliable model performance.

---

## 🏗️ CNN Architecture

| Layer | Configuration |
|------|--------------|
| Conv2D | 32 filters, 3×3 kernel |
| ReLU | Activation |
| MaxPooling | 2×2 |
| Conv2D | 64 filters, 3×3 kernel |
| ReLU | Activation |
| MaxPooling | 2×2 |
| Fully Connected | 128 neurons |
| Output Layer | 10 classes |

**Training Setup**
- **Loss Function:** CrossEntropyLoss  
- **Optimizer:** Adam  
- **Framework:** PyTorch  

---

## 🚀 Model Training
- **Batch Size:** 64  
- **Epochs:** 5  
- **Metrics Tracked:** Training & validation loss, accuracy  
- **Visualization:** Loss and accuracy curves per epoch  

---

## 📊 Evaluation & Results

### ✔ Training Loss Curve
<p align="center">
  <img src="images/curve.png" width="600">
</p>

### ✔ Confusion Matrix (Test Set)
<p align="center">
  <img src="images/matrix.png" width="600">
</p>

### ✔ Real-World Smartphone Predictions
<p align="center">
  <img src="images/prediction.png" width="700">
</p>

### ✔ Visual Error Analysis (Incorrect Predictions)
<p align="center">
  <img src="images/wrongPrediction.png" width="700">
</p>

---

## 📱 Real-World Prediction Pipeline
The trained CNN is evaluated on **custom smartphone images** by:

1. Loading images from the GitHub repository  
2. Applying the **same preprocessing pipeline** used during training  
3. Running inference in `.eval()` mode  
4. Applying **Softmax** to obtain class probabilities  

Each prediction includes:
- Predicted class label  
- Confidence percentage  

---

## 🔍 Model Observations & Analysis

- Very high confidence (**≈99–100%**) is observed for clean, well-aligned images, especially for **Bag** and **Sneaker**.
- Moderate confidence (**≈35–85%**) appears in visually similar classes such as **Pullover**, **Coat**, and **Dress**.
- Prediction confidence decreases with poor lighting, low contrast, or background noise.
- Despite being tra
