
# Efficient Time Series Forecasting Using TinyML Models

**Research Internship Project | Indian Institute of Information Technology Lucknow**

**Author:** Muskan Agrawal  
**Research Supervisor:** Dr. Rahul Kumar Verma  
**Department:** Computer Science and Artificial Intelligence  
**Institution:** Indian Institute of Information Technology Lucknow (IIIT Lucknow)

---

## 📌 Overview

This research investigates the impact of signal preprocessing techniques on the accuracy and computational efficiency of lightweight machine learning models for time-series classification.

The study focuses on **Human Activity Recognition (HAR)** using sensor data from smartphones and wearable devices, with an emphasis on TinyML applications in resource-constrained environments.

A systematic evaluation of **13 preprocessing configurations** was conducted across **three benchmark datasets (UCI-HAR, PAMAP2, and WISDM)** using Logistic Regression, Decision Trees, and a lightweight 1D Convolutional Neural Network (TinyCNN).

The objective was to identify preprocessing and model combinations that balance classification accuracy, training efficiency, and inference latency for potential edge-device deployment.

## 🎯 Research Objectives

- Analyze the impact of filtering and downsampling on time-series classification performance.
- Compare classical machine learning models with lightweight deep learning architectures.
- Evaluate how the order of preprocessing operations influences accuracy and efficiency.
- Identify effective preprocessing strategies across datasets with different sensor characteristics.
- Study the trade-offs between classification accuracy and inference latency for TinyML applications.

## 📊 Datasets

Three publicly available Human Activity Recognition datasets were used.

| Dataset | Description | Sensor Features |
|---|---|---|
| **UCI-HAR** | Smartphone-based activity recognition involving six daily activities | 9 |
| **PAMAP2** | Physical activity monitoring using multiple wearable inertial sensors | 52 |
| **WISDM** | Smartphone accelerometer-based human activity recognition | 3 |

The datasets differ in sampling characteristics, feature dimensionality, and activity complexity, enabling a comparative evaluation of preprocessing strategies.

**Note:** The datasets are not included in this repository due to their size. They can be obtained from their respective public sources.

## 🔬 Methodology

### 1. Data Preprocessing

The study evaluates **13 preprocessing configurations** grouped into five categories:

| Category | Configurations |
|---|---|
| Raw Data | No preprocessing (baseline) |
| Filtering Only | Butterworth, Savitzky–Golay |
| Downsampling Only | Naive Downsampling, Mean Downsampling |
| Downsampling → Filtering | Four combinations of downsampling and filtering methods |
| Filtering → Downsampling | Four combinations of filtering and downsampling methods |

#### Filtering Techniques

- **Butterworth Low-Pass Filter:** Reduces high-frequency noise while preserving important signal components.
- **Savitzky–Golay Filter:** Smooths sensor signals while preserving local peaks and activity transitions.

#### Downsampling Techniques

- **Naive Downsampling:** Retains every alternate sample to reduce temporal resolution.
- **Mean Downsampling:** Averages consecutive samples to reduce dimensionality while preserving signal information.

### 2. Machine Learning Models

Three lightweight model architectures were evaluated:

**Logistic Regression**
- Linear classification model
- Low computational overhead
- Used as a lightweight baseline

**Decision Tree**
- Nonlinear, rule-based classifier
- Interpretable predictions
- Low inference latency

**TinyCNN**
- Lightweight 1D Convolutional Neural Network
- Captures temporal patterns in sensor signals
- Uses convolutional, pooling, and dense layers for activity classification

### 3. Evaluation Metrics

Each model and preprocessing combination was evaluated using:

- Classification Accuracy
- Training Time
- Inference Time
- Inference Time per Sample
- Composite Performance Score

The composite score combines accuracy and computational efficiency:

**Score = Accuracy − 0.1 × Inference Time − 0.000001 × Training Time**

This metric prioritizes classification accuracy while penalizing inference latency and, to a lesser extent, training time.

## 📈 Experimental Results

The best-performing configurations by classification accuracy for each dataset are summarized below.

| Dataset | Best Model | Best Preprocessing Strategy | Accuracy |
|---|---|---|---|
| **UCI-HAR** | TinyCNN | Naive Downsampling → Savitzky–Golay | **95.44%** |
| **PAMAP2** | TinyCNN | Savitzky–Golay → Naive Downsampling | **94.54%** |
| **WISDM** | Decision Tree | Mean Downsampling | **59.47%** |

### Key Findings

**1. Preprocessing improves model performance**

Appropriate filtering and downsampling strategies improved classification performance over raw-data baselines, although the extent of improvement varied across datasets.

**2. TinyCNN achieves strong classification accuracy**

TinyCNN achieved the highest accuracy on UCI-HAR and PAMAP2, demonstrating the effectiveness of compact convolutional architectures for structured sensor data.

**3. Simpler models can be more computationally efficient**

Decision Trees demonstrated very low inference times, making them attractive for latency-sensitive applications.

On PAMAP2, Logistic Regression achieved a higher composite performance score than TinyCNN despite having slightly lower classification accuracy.

**4. Preprocessing order matters**

The order of filtering and downsampling influenced model performance. Downsampling followed by filtering generally performed well on UCI-HAR and PAMAP2, although the optimal sequence depended on the dataset and model.

**5. Dataset characteristics influence model selection**

No single model or preprocessing configuration performed best across every dataset. Signal characteristics, feature dimensionality, and computational requirements should guide model selection.

## 📁 Repository Structure

    TinyML-Time-Series-Research/
    │
    ├── notebooks/
    │   ├── PAMAP2_final.ipynb
    │   ├── UCI-HAR_final.ipynb
    │   └── WISDM_final.ipynb
    │
    ├── paper/
    │   ├── research_paper.pdf
    │   └── research_report.pdf
    │
    └── README.md

## 📄 Research Paper and Report

**Research Title:** Efficient Time Series Forecasting Using TinyML Models

- 📄 [Read the Research Paper](paper/research_paper.pdf)
- 📑 [Read the Research Internship Report](paper/research_report.pdf)

The research paper presents the methodology, experimental configurations, performance comparisons, results, and conclusions of the study.

## 💻 Implementation

The experimental implementations are provided as Jupyter Notebooks:

- [UCI-HAR Implementation](notebooks/UCI-HAR_final.ipynb)
- [PAMAP2 Implementation](notebooks/PAMAP2_final.ipynb)
- [WISDM Implementation](notebooks/WISDM_final.ipynb)

Each notebook contains the implementation of preprocessing techniques, model training, evaluation, and experimental analysis for its respective dataset.

The notebooks are preserved from the completed research internship. Dataset files are not included, and local dataset paths may need adjustment to reproduce the experiments.

## 🛠️ Technologies Used

**Programming Language:** Python

**Libraries and Frameworks:**
- NumPy
- Pandas
- SciPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Jupyter Notebook

**Research Areas:**
- Tiny Machine Learning (TinyML)
- Time-Series Classification
- Human Activity Recognition
- Signal Processing
- Edge Computing
- Lightweight Deep Learning

## 🚀 Future Scope

Potential extensions of this research include:

- Model quantization and pruning for reduced memory consumption.
- Evaluation on physical microcontrollers and edge devices.
- Automated preprocessing pipeline selection.
- Exploration of additional lightweight neural network architectures.
- Multimodal sensor fusion for improved activity recognition.

## 🙏 Acknowledgment

I would like to express my gratitude to **Dr. Rahul Kumar Verma**, Assistant Professor at the Indian Institute of Information Technology Lucknow, for his guidance, encouragement, and valuable feedback throughout this research internship.

I also thank **IIIT Lucknow** for providing the academic environment and resources that supported this work.

---

**Research Internship Project | IIIT Lucknow | 2026**

*This repository documents the research paper and experimental implementations developed during my undergraduate research internship.*
