# Ambulift AI Safety System

This repository contains the source code, model configurations, and edge deployment tools for an AI-powered accident detection and safety alert system for airport ambulifts.

## 📦 Repository Structure

```bash
ambulift_ai_safety_system/
├── README.md
├── requirements.txt
├── models/
│   ├── yolo_config.yaml
│   └── fall_detection_model.pt
├── src/
│   ├── main.py
│   ├── detection.py
│   ├── pose_estimation.py
│   ├── fall_detection.py
│   ├── alert_system.py
│   ├── video_stream.py
│   └── utils.py
├── data/
│   └── sample_videos/
├── configs/
│   └── system_config.yaml
├── dashboard/
│   └── ui.py
└── deployment/
    ├── edge_device_setup.sh
    └── docker-compose.yml
```

## 🧠 Components Overview

### `src/main.py`
Entry point to start the real-time processing loop with camera feeds.

### `src/detection.py`
Uses YOLOv8 or YOLO-NAS to detect aircraft, ambulift, personnel, stretchers, wheelchairs, and ground obstacles.

### `src/pose_estimation.py`
Implements OpenPose or MediaPipe to estimate body keypoints of caretakers or patients.

### `src/fall_detection.py`
LSTM-based classifier for detecting vertical fall motions and abnormal body posture changes.

### `src/alert_system.py`
Contains logic to filter detections and trigger alerts (buzzer, mobile notification, dashboard indicators).

### `src/video_stream.py`
Connects to local or IP cameras and manages frames for inference.

### `src/utils.py`
Includes utility functions for bounding box drawing, timestamp logging, and frame processing.

## 🖥️ Dashboard
- Built in `dashboard/ui.py` using Python and Streamlit (or optionally Flask).
- Live camera feed + object overlays
- Real-time alerts and logs display

## 📡 Deployment
- Edge-optimized using NVIDIA Jetson devices
- `deployment/edge_device_setup.sh` handles dependencies
- Optional `docker-compose.yml` for containerization

## ✅ To-Do
- [ ] Integrate DeepSORT for tracking
- [ ] Add GPS + IMU sensor support
- [ ] Cloud sync with MQTT
- [ ] Fine-tune fall detection on ambulift-specific data

## 📄 License
MIT License

---

This system is designed to enhance safety and operational awareness during passenger boarding with ambulifts. 

> Developed with ❤️ by Alper and Amber
