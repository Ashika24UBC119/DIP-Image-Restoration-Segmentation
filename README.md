# Comparative Analysis of Image Restoration and Segmentation Techniques for Noisy Images

## Digital Image Processing Mini Project

## 1. Problem Statement

Digital images are often affected by different types of noise during image acquisition and transmission. This project studies two common noise types, Gaussian noise and Salt-and-Pepper noise, and compares different spatial filtering techniques for restoring noisy images.

After restoration, image segmentation and edge detection techniques are applied to identify important image regions and boundaries. The performance of restoration techniques is evaluated using MSE, PSNR and SSIM, while segmentation performance is compared with BSDS500 ground-truth boundaries using IoU and Dice scores.

## 2. Objectives

- Study the effect of Gaussian and Salt-and-Pepper noise on images.
- Apply Mean, Median and Adaptive Median filtering techniques.
- Compare restoration techniques using MSE, PSNR and SSIM.
- Identify the best restoration method for each noise type.
- Apply Otsu thresholding and morphological operations for segmentation.
- Apply Canny edge detection for boundary extraction.
- Compare detected boundaries with BSDS500 ground-truth boundaries.
- Evaluate segmentation using IoU and Dice scores.
- Analyze the strengths and limitations of the implemented methods.

## 3. Dataset

The project uses the **Berkeley Segmentation Dataset 500 (BSDS500)**.

- Dataset: BSDS500
- Image type: Natural scene images
- Total dataset: 500 images
- Images evaluated in this project: 30 test images
- Ground truth: Human annotated boundary information
- Preprocessing: Images are converted to grayscale before noise addition and processing.

The complete dataset is not included in this repository because of its size.

## 4. Methodology

The overall workflow is:

**BSDS500 Images → Grayscale Conversion → Noise Addition → Image Restoration → Quality Evaluation → Segmentation → Edge Detection → Ground Truth Comparison → Performance Analysis**

### Noise Types

1. Gaussian Noise
2. Salt-and-Pepper Noise

### Restoration Techniques

1. Mean Filtering (5 × 5)
2. Median Filtering (5 × 5)
3. Adaptive Median Filtering

### Segmentation Techniques

1. Otsu Thresholding
2. Morphological Operations
3. Canny Edge Detection

### Evaluation Metrics

#### Restoration

- Mean Squared Error (MSE)
- Peak Signal-to-Noise Ratio (PSNR)
- Structural Similarity Index (SSIM)

#### Segmentation

- Intersection over Union (IoU)
- Dice Score

## 5. Implementation

The project is implemented using Python.

### Libraries Used

- NumPy
- OpenCV
- scikit-image
- SciPy
- Pandas
- Matplotlib

The experiment was executed using Google Colab.

The project evaluates 30 BSDS500 test images. Gaussian noise with a standard deviation of 25 and Salt-and-Pepper noise with an amount of 0.05 are added to the grayscale images.

For each noise type, Mean, Median and Adaptive Median filtering are applied and compared using restoration metrics.

The restored images are then processed using Otsu thresholding with morphological cleanup and Canny edge detection.

## 6. Results

### Restoration Results

| Noise Type | Best Method | MSE | PSNR (dB) | SSIM |
|------------|-------------|-----|-----------|------|
| Gaussian | Mean 5 × 5 | 281.6071 | 24.6632 | 0.6285 |
| Salt-and-Pepper | Adaptive Median | 131.1859 | 28.8163 | 0.8569 |

For restoration, lower MSE and higher PSNR and SSIM indicate better performance.

The results show that **Mean 5 × 5 filtering performed best for Gaussian noise**, while **Adaptive Median filtering performed best for Salt-and-Pepper noise**.

### Segmentation Results

| Noise Type | Restoration | IoU | Dice |
|------------|-------------|-----|------|
| Gaussian | Mean 5 × 5 | 0.0317 | 0.0601 |
| Salt-and-Pepper | Adaptive Median | 0.0276 | 0.0525 |

The segmentation scores are relatively low because the Canny edge map is compared directly with BSDS500 boundary annotations using strict pixel-level IoU and Dice measurements.

## 7. Limitations

- Only 30 test images were used for practical execution.
- Only Gaussian and Salt-and-Pepper noise were considered.
- Filtering performance depends on parameter selection.
- Mean filtering can blur image details.
- Natural images contain complex structures and multiple boundaries.
- Strict pixel-level comparison may penalize small differences in boundary location.
- Canny detection may produce extra edges that are not present in the ground-truth boundary map.

## 8. Future Scope

The project can be improved by:

- Using the complete BSDS500 dataset.
- Testing additional noise types such as Speckle, Rayleigh and Gamma noise.
- Comparing additional restoration techniques.
- Using advanced adaptive and frequency-domain filters.
- Applying deep learning based image restoration.
- Using advanced semantic or instance segmentation models.
- Using tolerance-based boundary evaluation.
- Developing a real-time image restoration and segmentation application.

## 9. Conclusion

This project demonstrates the effect of different noise types on digital images and compares spatial filtering techniques for image restoration.

The experimental results show that Mean 5 × 5 filtering performed best for Gaussian noise, while Adaptive Median filtering performed best for Salt-and-Pepper noise based on the restoration metrics.

Otsu thresholding, morphological operations and Canny edge detection were used for segmentation and boundary extraction. Although the strict IoU and Dice scores were low, the project demonstrates the complete process of image restoration, segmentation and quantitative evaluation.

Overall, the project shows that the choice of restoration technique should depend on the type of noise present in the image.

