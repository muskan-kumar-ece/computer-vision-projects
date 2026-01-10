# 🚗 Abnormal Driving Behavior Detection using Computer Vision (YOLOv8 + Trajectory Analysis)

A real-time computer vision project to detect **abnormal / risky driving behaviors** in traffic videos using:
- **YOLOv8** for vehicle detection
- **ByteTrack** for multi-object tracking (stable vehicle IDs)
- **Trajectory-based motion features** (speed variation, direction changes, lateral jerk)
- Automated **evidence capture** and **CSV reporting**

This project generates an output video with:
- 🟩 Normal vehicles (green)
- 🟥 Abnormal vehicles (red)
- Vehicle ID + abnormal score overlay

---

## 📌 Project Overview

Abnormal driving in traffic videos often appears as:
- Sudden acceleration / braking
- Rash turning or zig-zag motion
- Aggressive lateral shifting

This system detects such behavior by analyzing **vehicle trajectories over time** and computing an abnormality score.

---

## 🎯 Key Features

✅ Vehicle detection using **YOLOv8**  
✅ Multi-object tracking using **ByteTrack** (stable IDs)  
✅ Vehicle trajectory extraction using centroid tracking  
✅ Abnormal behavior scoring using:
- Speed variation
- Direction change
- Lateral jerk  
✅ Smoothing to reduce flickering false detections  
✅ Event-based evidence saving (`/evidence/`)  
✅ CSV event report (`abnormal_report.csv`)  
✅ Vehicle-level summary report (`vehicle_abnormal_summary.csv`)  
✅ Output annotated demo video (`output_abnormal_detection.mp4`)

---

## 🧠 Methodology

### Step 1: Vehicle Detection
YOLOv8 detects objects in each frame.  
Only vehicle classes are considered:
- Car
- Motorcycle
- Bus
- Truck

---

### Step 2: Vehicle Tracking (ByteTrack)
Tracking ensures each vehicle gets a **unique stable ID** across frames:
- ID: 11 stays ID: 11 over time
- Enables motion history per vehicle

---

### Step 3: Trajectory Extraction
For each tracked vehicle:
- Extract bounding box centroid `(cx, cy)`
- Store last `N` centroid points as trajectory

---

### Step 4: Feature Computation
For each vehicle trajectory, compute:

#### ✅ 1) Speed variation
\[
SpeedVar = std(speed)
\]

#### ✅ 2) Direction change
\[
DirChange = |\Delta \theta|
\]

#### ✅ 3) Lateral jerk (aggressive side movement)
\[
Jerk = |\Delta acceleration|
\]

---

### Step 5: Abnormal Score
Final abnormality score:

\[
Score = \alpha(SpeedVar) + \beta(DirChange) + \gamma(Jerk)
\]

Default weights:
- \(\alpha = 0.4\)
- \(\beta = 0.3\)
- \(\gamma = 0.3\)

If:
\[
Score > 0.6 \Rightarrow Abnormal
\]

---

## 📂 Output Files

After running, you get:

output_abnormal_detection.mp4
abnormal_report.csv
vehicle_abnormal_summary.csv
evidence/
vehicle_11_event_frame_223.jpg
vehicle_29_event_frame_320.jpg


---

## 📊 Example CSV Output (Event-Level Report)

| vehicle_id | frame_id | timestamp_sec | smooth_abnormal_score | evidence_path |
|----------|----------|---------------|------------------------|---------------|
| 11 | 223 | 7.43 | 0.772 | evidence/vehicle_11_event_frame_223.jpg |
| 29 | 320 | 10.67 | 0.673 | evidence/vehicle_29_event_frame_320.jpg |

---

## 🛠 Tech Stack

- Python
- OpenCV
- Ultralytics YOLOv8
- ByteTrack Tracker
- NumPy
- Pandas
- Matplotlib

---

## 🚀 How to Run

### 1️⃣ Install dependencies
```bash
pip install ultralytics opencv-python numpy pandas matplotlib



---

## ✅ Next (Recommended)
If you want, I can also create for you:

### ✅ 1) GitHub Repo Structure
(best practice folders + outputs)

### ✅ 2) “How it works” diagram for README
(block diagram figure)

### ✅ 3) LinkedIn post to publish this project 🔥

Just tell me what you want next.

