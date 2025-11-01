# Gloved-vs-Bare-Hand-Detection-using-YOLOv8
This project focuses on detecting **whether a person is wearing gloves or not** in industrial environments using the **YOLOv8 object detection model**.  
It aims to improve **safety compliance** by automatically identifying unprotected (bare) hands in real-time camera feeds or recorded videos.

---

## 🚀 Project Overview

- **Objective:** Detect and classify hands into two categories — `Gloves` and `NO-Gloves` (Bare Hands).
- **Use Case:** Useful for **industrial safety monitoring**, **factory PPE compliance**, and **workplace automation**.
- **Framework Used:** [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- **Language:** Python 3.11
- **Environment:** Anaconda (Spyder) + Kaggle GPU for training

---

## 🗂️ Folder Structure

Glove vs Bare Hand Detection Project/
│
├── data/ # Dataset (train, valid, test) in YOLO format
├── input/ # Input videos or images for inference
├── output/ # Results after detection (annotated videos/images)
├── logs/ # Training and evaluation logs
├── Python Scripts/ # Scripts for training, testing, and inference
├── best_glove_model.pt # Trained YOLOv8 model
├── data.yaml # Dataset configuration
└── README.md # Project documentation

yaml
Copy code

---

## 🧩 Dataset Details

- **Source:** PPE Safety Dataset (Kaggle) + 60 manually annotated images via Roboflow  
- **Classes:**  
0: Gloves
1: NO-Gloves

yaml
Copy code
- **Total Images:** 3312  
- Train: 2346  
- Validation: 646  
- Test: 320  

---

## ⚙️ Model Training

- **Model Used:** YOLOv8 (Ultralytics v8.3.2)
- **Training Parameters:**
- Epochs: 10
- Image size: 640x640
- Batch size: 16
- Optimizer: AdamW
- Device: Kaggle GPU (Tesla T4)

**Performance Metrics (Validation Set):**
| Metric     | Score |
|-------------|--------|
| mAP50       | 0.704 |
| mAP50-95    | 0.443 |
| Gloves (mAP50)     | 0.777 |
| NO-Gloves (mAP50)  | 0.631 |

---

## 🧪 Running Inference

You can run detection on videos or images using the trained model:

```python
from ultralytics import YOLO

model = YOLO("F:/glove_detection_project/Python Scripts/best_glove_model.pt")

# Run inference on a video
results = model.predict(source="C:/Users/DELL/Dropbox/PC/Downloads/12.mp4", show=True, conf=0.5)
Output videos will appear inside your output/ folder.


🧰 Tools & Libraries
Python 3.11

Ultralytics YOLOv8

OpenCV

Roboflow

PyTorch

Anaconda (Spyder IDE)

💡 Future Improvements
Train for more epochs (15–30) to improve mAP

Experiment with Faster R-CNN for comparison

Implement real-time detection via webcam

Add alert system when bare hands are detected

👨‍💻 Author

Rithik Cyber
Master’s in Artificial Intelligence & Machine Learning

Acknowledgments


Ultralytics YOLOv8
Kaggle PPE Detection Dataset
Roboflow Annotation Tool

