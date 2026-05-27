# cobb-angle-estimation
Automatic Cobb angle estimation in spine AP view X-rays using YOLOv11-Pose 
# Automatic Cobb Angle Estimation in Spine X-rays using YOLOv11-Pose

**Course:** Temas Selectos de Física (Machine Learning)  
**Professor:** Dr. Luis Carlos Padierna García  
**Institution:** Universidad de Guanajuato, División de Ciencias e Ingenierías  
**Year:** 2026

---

## Description

This project proposes an open-source solution based on **YOLOv11-Pose**  for the automatic estimation of Cobb angles (PT, MT, TL) from anteroposterior (AP) spine radiographs. The model detects the anatomical keypoints of the 17 thoracic and lumbar vertebrae and calculates the angles using Euclidean geometry.

The clinical reference software in the United States (EOS imaging with spineEOS) has an installation cost of approximately $950,000 USD. This project proposes an accessible open-source alternative.

---

## Results

| Metric | PT | MT | TL | Total |
|---|---|---|---|---|
| MAE (°) | 4.90° | 4.67° | 4.36° | **4.64°** |
| SMAPE (%) | 87.37%* | 32.87% | 34.45% | 51.56%* |

*High SMAPE in PT due to 394 images with PT ground truth = 0.0°

**Clinical threshold: MAE < 5° is considered acceptable**

### MAE by scoliosis severity

| Severity | MAE MT |
|---|---|
| Normal (<10°) | 2.79° |
| Mild (10–25°) | 4.29° |
| Moderate (25–40°) | 5.84° |
| Severe (>40°) | 8.71° |

---

## Model Comparison

| Model | Hardware | Epochs | MAE Total |
|---|---|---|---|
| **v1 (selected)** | GTX 1650 Ti | 50 | **4.64°** |
| v1e100 | Tesla T4 (Colab) | 58 | 4.65° |
| v1e100_2 | Tesla T4 (Colab) | 50 | 4.67° |

---

## Dataset

This project uses the **Spinal-AI2024** dataset:
- 20,000 synthetic AP spine X-ray images
- 68 keypoints per image (4 corners × 17 vertebrae)
- 3 Cobb angles ground truth per image (PT, MT, TL)

Download: https://github.com/Ernestchenchen/Spinal-AI2024

> **Note:** The dataset images are NOT included in this repository
> due to size constraints. Download them from the link above.

---

## Pipeline
