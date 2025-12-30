# Lane Change Violation Detection using Computer Vision

## 📌 Overview
This project demonstrates a computer vision–based approach to detect unsafe or illegal lane change behavior from traffic video data. The system analyzes vehicle motion patterns and indicator usage to identify potential lane change violations.

The implementation is designed as a **demo-level academic project**, focusing on clarity, reproducibility, and explainability.

---

## 🎯 Objectives
- Detect vehicles from rear-view traffic video
- Track vehicle trajectories across frames
- Analyze lateral movement for lane change detection
- Recognize turn indicator blinking behavior
- Flag potential lane change violations for review

---

## 🧠 Methodology (High-Level)
1. Input traffic video is processed frame-by-frame  
2. Vehicles are detected using a deep learning–based object detector  
3. Multi-object tracking is applied to maintain vehicle identities  
4. Trajectory analysis is used to detect lane change motion  
5. Indicator blinking patterns are analyzed using color-based features  
6. Detected events are logged as potential violations  

---

## 🛠 Tools & Technologies
- Python  
- OpenCV  
- YOLO (object detection)  
- SORT / DeepSORT (object tracking)  
- Google Colab  

---

## 📂 Project Structure
lane-change-violation-detection/
├── demo_video/ # Input and output demo videos
├── output_results/ # Images, logs, and detection results
├── colab_notebook/ # Google Colab implementation
└── README.md

---

## ⚠️ Disclaimer
This project is intended for **academic demonstration and research purposes only** and does not represent a deployed traffic enforcement system.



