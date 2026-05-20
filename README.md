# 🎨 Cartoonization Pipeline (Edge-Aware Image Stylization)

A computer vision pipeline that converts real-world images into a **cartoon / vector-style representation** using edge detection, color quantization, and image filtering techniques.

---

## 🧠 Overview

This project separates an image into:
- **Structural information (edges)**
- **Color information (simplified regions)**

Then fuses them to generate a stylized cartoon-like output.

---

## ⚙️ Pipeline Steps

### 1. Image Preprocessing
- Resize image to fixed width (500px)
- Maintain aspect ratio for consistent processing

### 2. HSV Color Enhancement
- Convert image to HSV color space
- Boost:
  - Saturation (+10%)
  - Brightness (+40%)

### 3. Edge Detection
- Convert to grayscale
- Apply median blur (noise reduction)
- Detect edges using Canny algorithm
- Dilate edges for stronger contours
- Invert edge mask for blending

### 4. Color Simplification
- Apply bilateral filter (edge-preserving smoothing)
- Use K-Means clustering (K=5)
- Reduce image to flat color regions (posterization effect)

### 5. Stylization Fusion
Two output variants are generated:
- Edge-masked cartoon effect
- Alternative inverted mask rendering

---

## 🧪 Output

- `cartoon_effect_and` → clean cartoon/vector look  
- `cartoon_effect_not` → alternative stylized version  
- `edges_inv` → extracted edge map  

---

## 📷 Example
<img width="1790" height="520" alt="image" src="https://github.com/user-attachments/assets/2c23d442-cf53-40c5-a19f-3730f0028842" />
<img width="1584" height="590" alt="image" src="https://github.com/user-attachments/assets/234d6472-1b9f-4285-bb2c-e6cce1ee4443" />

