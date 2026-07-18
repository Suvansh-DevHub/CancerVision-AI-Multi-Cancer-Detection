# 🩺 CancerVision

![Python](https://img.shields.io/badge/Python-3.10-blue) ![TensorFlow](https://img.shields.io/badge/TensorFlow-DeepLearning-orange) ![Flask](https://img.shields.io/badge/Flask-WebApp-black) ![License](https://img.shields.io/badge/License-MIT-green)

### AI-Based Multi-Cancer Detection & Subtype Classification System

CancerVision is an AI-powered medical image analysis platform designed to detect multiple types of cancer and classify their subtypes using Deep Learning. The system analyzes medical images from different organs and automatically routes them to specialized AI models for accurate prediction.

The platform combines automated organ identification, multi-model inference, explainable AI (Grad-CAM), AI-assisted clinical recommendations, and downloadable PDF reports into a single unified application.

---

## 📌 Features

- 🧠 Automatic organ detection using a Gatekeeper Model
- 🫁 Lung Cancer Detection & Subtype Classification
- 🧠 Brain Tumor Detection & Classification
- 🎗 Breast Cancer Detection
- 🩹 Skin Cancer Detection & Classification
- 📊 Confidence score for every prediction
- 🔥 Grad-CAM visual explainability
- 🤖 AI-generated and rule-based clinical recommendations
- 📄 Downloadable PDF diagnostic reports
- ⚡ Asynchronous background processing using Celery
- 📋 Inference logging for future analysis
- 🔒 Secure Flask backend with validation and CSRF protection

---

# Supported Organs

| Organ | Imaging Modality | Prediction |
|---------|-----------------|------------|
| Lung | CT Scan, Chest X-ray | Cancer Detection + Subtype |
| Brain | MRI | Tumor Detection + Subtype |
| Breast | Mammography | Cancer Detection |
| Skin | Dermoscopy | Cancer Detection + Subtype |

---

# Supported Cancer Types

### Lung
- Adenocarcinoma
- Large Cell Carcinoma
- Squamous Cell Carcinoma
- Normal

### Brain
- Glioma
- Meningioma
- Pituitary Tumor
- Normal

### Breast
- Cancer
- Normal

### Skin
- Basal Cell Carcinoma
- Melanoma
- Normal

---

# System Architecture

```
                    Medical Image
                          │
                          ▼
               Unified Preprocessing
                          │
                          ▼
                Gatekeeper AI Model
                          │
      ┌──────────┬──────────┬──────────┬──────────┐
      ▼          ▼          ▼          ▼
   Lung AI    Brain AI   Breast AI   Skin AI
      │          │          │          │
      └──────────┴──────────┴──────────┘
                    │
                    ▼
         Cancer Detection & Classification
                    │
                    ▼
           Confidence Score Generation
                    │
                    ▼
              Grad-CAM Explanation
                    │
                    ▼
      Clinical Recommendation Engine
                    │
                    ▼
          PDF Report Generation
```

---

# Workflow

1. User uploads medical image(s).
2. Basic patient information is provided.
3. Images are preprocessed automatically.
4. Gatekeeper identifies the organ.
5. Appropriate AI model performs inference.
6. Cancer detection is performed.
7. Subtype classification (where applicable).
8. Confidence score is calculated.
9. Grad-CAM heatmap is generated.
10. Clinical recommendations are produced.
11. Structured PDF report is generated.
12. Results are displayed to the user.

---

# Key Components

## Gatekeeper Model

The Gatekeeper model automatically identifies the organ from the uploaded image and routes it to the appropriate specialized AI model.

This eliminates manual organ selection and creates a fully automated prediction pipeline.

---

## Specialized Deep Learning Models

Each organ uses its own optimized deep learning model trained specifically for its imaging characteristics.

- Lung Model
- Brain Model
- Breast Main Model
- Breast Fallback Model
- Skin Model

---

## Explainable AI

To improve transparency and interpretability, CancerVision generates Grad-CAM heatmaps highlighting image regions that contribute most to the model's prediction.

---

## Recommendation Engine

The platform combines:

- Rule-based recommendations
- AI-generated recommendations

to provide structured clinical guidance after prediction.

---

## PDF Report

Each analysis generates a downloadable PDF containing:

- Patient Information
- Prediction Result
- Cancer Type
- Confidence Score
- Model Used
- Grad-CAM Visualization
- Clinical Recommendations

---

## Asynchronous Processing

Long-running AI inference tasks are processed in the background using:

- Celery
- Redis

This keeps the user interface responsive during analysis.

---

# Technology Stack

## Backend

- Python
- Flask
- Celery
- Redis

## Deep Learning

- TensorFlow
- Keras
- MobileNet
- Custom CNN Models

## Computer Vision

- OpenCV
- Pillow
- NumPy
- Grad-CAM

## Frontend

- HTML
- CSS
- JavaScript

## Report Generation

- ReportLab

---

# Project Structure

```
CancerVision/
│
├── app.py
├── tasks.py
├── mycode.py
├── gradcam.py
├── recommendation_engine.py
├── report_generator.py
├── inference_logger.py
├── config.py
├── requirements.txt
│
├── models/
│   ├── Brain/
│   ├── Breast/
│   ├── Lung/
│   ├── Skin/
│   └── Gatekeeper/
│
├── static/
├── templates/
├── reports/
├── logs/
└── uploads/
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/yourusername/CancerVision.git
```

Move into project directory

```bash
cd CancerVision
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run Redis

```bash
redis-server
```

Start Celery Worker

```bash
celery -A tasks worker --loglevel=info
```

Run Flask Application

```bash
python app.py
```

---

# Future Improvements

- Docker Deployment
- Cloud Deployment (AWS)
- Multi-user Authentication
- DICOM File Support
- Electronic Health Record Integration
- Additional Cancer Types
- REST API
- Mobile Application
- Real-time Monitoring Dashboard

---

# Disclaimer

CancerVision is intended for research and educational purposes only.

The predictions generated by the system are AI-assisted estimates and should **not** be considered a substitute for professional medical diagnosis or clinical decision-making.

---

# Author

**Suvansh**

Final Year B.Tech (Computer Science & Engineering)

AI • Deep Learning • Medical Image Analysis
