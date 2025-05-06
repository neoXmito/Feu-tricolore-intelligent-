# AI Traffic Management System

This repository is part of an ongoing open‑source research effort to develop an intelligent, adaptive traffic‑light control system. It combines state‑of‑the‑art object‑detection algorithms (e.g., YOLOv5) with custom IoT designs using platforms like Wokwi and Arduino. Please note that all code and models are in active development and may change.

I am currently working on adding a feature to prioritize emergency vehicles—this is the main focus of the project.

The core of the system is an embedded AI module that uses computer vision to assess vehicle density in each lane of an intersection and dynamically adjusts green/red signal durations to optimize traffic flow.

The YOLOv5s model has been chosen for its balance of speed, efficiency, and accuracy. You can find the official implementation here: [https://github.com/ultralytics/yolov5](https://github.com/ultralytics/yolov5)

---

## Features

* **Vehicle Detection & Counting**
  Analyze a live camera feed to detect and count cars, buses, trucks, and bikes in each lane.
* **Adaptive Signal Timing**
  Calculate green/red light intervals based on real‑time lane density comparisons.
* **Emergency Vehicle Priority**
  *(In development)* Modify light sequences on‑the‑fly to give priority passage to ambulances, fire trucks, and police vehicles.
* **Simulation Display**
  Visualize traffic flows and signal timing in a Pygame‑based simulator.

---

## Hardware & Devices

* **Processor:** NVIDIA Jetson Nano
* **Camera:** IP camera for real‑time video capture

---

## Getting Started

### CPU & GPU (ONNX)

```bash
cd implementation_with_yolov5s_onnx_model
python3 main.py --sources video1.mp4,video2.mp4,video3.mp4,video5.mp4
```

### GPU Only (TensorRT)

```bash
cd implementation_with_yolov5s_tensorrt_model
python3 main.py --sources video1.mp4,video2.mp4,video3.mp4,video5.mp4
```

---

## Pygame Simulation

A custom simulation illustrates vehicles moving through an intersection with timed traffic lights. Recent enhancements include:

* **Turning Movements:** Vehicles can go straight, turn left, or turn right.
* **Vehicle‑Type Selection:** Choose which vehicle classes (car, bus, truck, bike) appear in the simulation.
* **Randomized Green‑Signal Duration:** Optionally assign green intervals randomly within a user‑defined range.

---

## References

1. **YOLOv5 → ONNX Export:**
   [https://github.com/ultralytics/yolov5](https://github.com/ultralytics/yolov5)
2. **ONNX → TensorRT Conversion:**
   [https://github.com/SeanAvery/yolov5-tensorrt](https://github.com/SeanAvery/yolov5-tensorrt)
