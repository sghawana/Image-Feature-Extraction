# SIFT Feature Extraction from Scratch

## Introduction
This repository contains an implementation of the **Scale-Invariant Feature Transform (SIFT)** algorithm from scratch. Additionally, the project analyzes how various standard transformations (such as rotation, blur, scaling, etc.) impact the number of detected features.

---

## Methodology
### 1. Scale-Invariant Feature Transform (SIFT)
SIFT is a robust feature detection and description algorithm commonly used in computer vision tasks. It identifies distinctive keypoints in an image that remain invariant to scaling, rotation, and some forms of affine transformations.

#### **Steps of the SIFT Algorithm:**
1. **Scale-Space Construction**
   - The image is progressively blurred using a Gaussian filter to create a scale-space representation:<br>
     $$L(x, y, \sigma) = I(x, y) * G(x, y, \sigma)$$<br>
     where $G(x, y, \sigma)$ is a Gaussian kernel with standard deviation $\sigma$.
2. **Difference of Gaussian (DoG) Computation**
   - The Difference of Gaussian (DoG) is computed to detect potential keypoints:<br>
     $$D(x, y, \sigma) = L(x, y, k\sigma) - L(x, y, \sigma)$$<br>
3. **Keypoint Localization**
   - Extrema are detected in DoG images by comparing a pixel with its 26 neighbors across adjacent scales.
4. **Orientation Assignment**
   - A histogram of gradient orientations around each keypoint is computed to assign a dominant orientation.
5. **Keypoint Descriptor Generation**
   - A 128-dimensional descriptor is created by computing histograms of gradient magnitudes and orientations in 16 sub-regions.

### 2. Impact Analysis of Transformations
To analyze how transformations affect feature detection, we applied:
- **Rotation:** Images are rotated at different angles (e.g., 15°, 30°, 45°, etc.).
- **Blur:** Gaussian blur is applied with varying kernel sizes.
- **Scaling:** Images are resized at different scales.
- **Brightness Change:** Image intensity is adjusted to test illumination invariance.

The number of keypoints detected under each transformation is recorded and visualized.

---

## Results
refer to report.pdf for results


