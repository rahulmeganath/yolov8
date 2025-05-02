# 🚦 Intelligent Object Counting and Speed Monitoring System using YOLOv8

A real-time web-based surveillance system for **object detection**, **object tracking**, **region-wise counting**, and **speed estimation** using **YOLOv8**. The system is built using **Flask** and containerized with **Docker** for easy deployment.

---

## 🎯 Features

- 🧠 **YOLOv8 Object Detection**
- 🎯 **Object Tracking** using ByteTrack/DeepSORT
- 🔄 **Global Object Counting** based on unique object IDs
- 📍 **Region-based Counting** (define entry/exit lines)
- ⏱️ **Speed Estimation** in pixels/second
- 🌐 **Web Interface** with Flask for video upload and results
- 📦 **Docker Support** for easy deployment

---

## ⚙️ How It Works

### ✅ Global Count
Each object is assigned a unique ID. If the ID hasn't been seen before, it is added to a set for global counting.

### ✅ Region-Based Count
A horizontal line is defined in the frame. If an object moves across this line (top to bottom), and it hasn't been counted already, it's added to the region count.

### 💨 Speed Estimation
Speed is calculated using:

```text
Speed = Distance (in pixels) / Time (in seconds)
```

---

## 🔧 Prerequisites

- Python 3.8+
- pip
- (Optional) Docker installed and running

---

## 🧪 Run Locally (Without Docker)

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/yolo-flask-app.git
cd yolo-flask-app
```

### 2. Create Virtual Environment
```
python -m venv yolov8-env
#Activate:
yolov8-env\Scripts\activate
```
### 3. Install Dependencies
```
pip install -r requirements.txt
```
### 3. Run the Flask App

```
python app.py
```

### Run Using Docker
## 1. Build the Docker Image
```
docker build -t yolo-flask-app .
```
## 2. Run the Container
```
docker run -p 5000:5000 yolo-flask-app
```

## Future Improvements

  -  Real-world speed (m/s) via camera calibration

  -  Drawn polygons for flexible region definitions

  -  Chart dashboard (counts/speed over time)

  -  Support for live webcam and RTSP/IP camera input

  -  Store results in a database
