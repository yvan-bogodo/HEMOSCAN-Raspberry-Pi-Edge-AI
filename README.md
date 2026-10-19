# HEMOSCAN - Non-Invasive Hemoglobin Estimation from Fingernail Images

**Low-cost anemia screening from a smartphone/Raspberry Pi photo of the fingernail - Douala, Cameroon.**

HEMOSCAN is a Physical AI project: turning a noisy, real-world camera image (fingernail) into a reliable medical signal (hemoglobin level).

### The Problem
Anemia detection usually needs a blood test. It's expensive and inaccessible. Nail pallor is a known clinical sign, but subjective. Can we automate it with CV?

### What I Built (End-to-End)

**1. Data & Real-World Complexity:**
- Collected dataset of fingernail images with diverse skin tones, lighting conditions
- Custom annotation & color calibration pipeline
- Challenge: Sim-to-Real - skin tone bias, ambient light, shadows, nail polish

**2. Model & Evaluation (Evaluation-First):**
- Stack: MobileNet V3, PyTorch, OpenCV
- Approach: Image segmentation (nail bed isolation) -> Color feature extraction -> Regression/Classification for hemoglobin level
- Training: Transfer learning, color augmentation, white-balance normalization
- Metrics: MAE for hemoglobin estimation, sensitivity/specificity for anemia

**3. Edge Deployment (Physical AI Core):**
- Optimization: Model quantized to TFLite for Raspberry Pi / Mobile
- Inference: <2s on Pi 4 / Android
- Real-world challenges solved: auto white-balance, nail detection with blur, low-light performance

**4. Observability:**
- Logging of failure cases (e.g., nail polish, poor lighting) for continuous evaluation

This mirrors Artha Labs' mission: Data -> Robust Eval -> Simulation (synthetic lighting/skin tones) -> Edge Deploy.

### Tech Stack
`Python, PyTorch, MobileNetV3, OpenCV, Image Segmentation, Color Science, Raspberry Pi, TFLite`

### Next Steps
- 3D reconstruction of nail for better light modeling
- Synthetic data generation with Isaac Sim / Blender for skin tone diversity
- Integration into a full vitals pipeline

---
**Author:** Yvan Steve Kingsley BOGODO EBOUEME - Biomedical Engineer | ML Engineer
**Contact:** +237 658047817 | yvan71072@icloud.com
**Location:** Douala, Cameroon - Open to Remote
