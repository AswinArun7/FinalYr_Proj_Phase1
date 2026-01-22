# Final Year Project - Phase 1: YOLOv5 Object Detection

## Project Overview
This repository contains the implementation of YOLOv5 object detection model for my final year project. The project demonstrates real-time object detection capabilities using pre-trained models on both static images and live webcam feeds.

## Original Repository
This project is based on the official **Ultralytics YOLOv5** repository:
- **Original Repo**: [ultralytics/yolov5](https://github.com/ultralytics/yolov5)
- **Documentation**: [YOLOv5 Docs](https://docs.ultralytics.com/yolov5/)
- **License**: AGPL-3.0

For detailed information about YOLOv5 architecture, training, and advanced features, refer to [README_ULTRALYTICS.md](README_ULTRALYTICS.md).

---

## Setup and Installation

### Prerequisites
- Python 3.8 or higher (tested with Python 3.13.0)
- Git
- Webcam (for live detection)

### Step 1: Clone the Repository
```bash
git clone https://github.com/AswinArun7/FinalYr_Proj_Phase1.git
cd FinalYr_Proj_Phase1
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

**Key dependencies installed:**
- PyTorch 2.6.0+cpu
- torchvision
- OpenCV
- NumPy, Matplotlib, Pandas
- Ultralytics

### Step 3: Verify Installation
The repository includes a pre-trained YOLOv5s model (`yolov5s.pt`) ready for inference.

---

## My Work: Object Detection Implementation

### 1. Image Detection
Successfully implemented object detection on static images using the YOLOv5s model.

**Command:**
```bash
python detect.py --weights yolov5s.pt --source data/images --conf 0.25
```

**Results:**
- Processed sample images (bus.jpg, zidane.jpg)
- Detected objects: persons, vehicles, accessories
- Output saved to `runs/detect/exp*/`

### 2. Live Webcam Detection
Implemented real-time object detection using webcam feed.

**Command:**
```bash
python detect.py --weights yolov5s.pt --source 0 --conf 0.25
```

**Performance:**
- Resolution: 1280x720 @ 30 FPS
- Inference Speed: ~100-200ms per frame (CPU)
- Successfully detected: persons, ties, laptops, and other objects in real-time

**To stop detection:** Press 'q' or close the window

### 3. Custom Detection Options

#### Detect on Video File
```bash
python detect.py --weights yolov5s.pt --source path/to/video.mp4
```

#### Detect on Directory of Images
```bash
python detect.py --weights yolov5s.pt --source path/to/images/
```

#### Adjust Confidence Threshold
```bash
python detect.py --weights yolov5s.pt --source 0 --conf 0.4
```

---

## Model Information

### YOLOv5s (Small)
- **Parameters**: 7.2M
- **Size**: ~14 MB
- **Speed**: Fast inference suitable for real-time applications
- **Accuracy**: Good balance between speed and accuracy
- **Use Case**: Real-time detection on CPU

### Other Available Models
- `yolov5n.pt` - Nano (fastest, smallest)
- `yolov5m.pt` - Medium (better accuracy)
- `yolov5l.pt` - Large (high accuracy)
- `yolov5x.pt` - Extra Large (best accuracy, slower)

---

## Project Structure
```
yolov5/
├── data/               # Dataset configurations and sample images
├── models/             # Model architecture definitions
├── utils/              # Utility functions
├── detect.py           # Detection script (main work)
├── train.py            # Training script
├── val.py              # Validation script
├── requirements.txt    # Python dependencies
├── yolov5s.pt         # Pre-trained model weights
└── runs/              # Detection results (gitignored)
```

---

## Results and Observations

### Successful Detections
✅ Person detection with high confidence  
✅ Object detection (laptop, tie, etc.)  
✅ Real-time processing on webcam  
✅ Accurate bounding box placement  

### Performance Metrics
- **Inference Time**: 100-200ms per frame (CPU)
- **Pre-processing**: ~3-4ms
- **NMS**: ~13-16ms
- **FPS**: 5-10 FPS on CPU

---

## Important Notes

### Python Environment
This project uses **Python 3.13** located at:
```
C:\Users\Aswin Arun\AppData\Local\Programs\Python\Python313\python.exe
```

If you have multiple Python installations, use the full path:
```bash
C:\Users\Aswin Arun\AppData\Local\Programs\Python\Python313\python.exe detect.py --weights yolov5s.pt --source 0
```

### Gitignore
The following are excluded from version control:
- `runs/` - Detection output results
- `.venv/` - Virtual environment
- `*.pt` files (except yolov5s.pt) - Large model weights
- `__pycache__/` - Python cache files

---

## Future Work
- [ ] Train custom model on specific dataset
- [ ] Optimize for GPU acceleration
- [ ] Implement object tracking
- [ ] Deploy as web application
- [ ] Add custom object classes

---

## References
- [YOLOv5 Official Documentation](https://docs.ultralytics.com/yolov5/)
- [Ultralytics GitHub](https://github.com/ultralytics/yolov5)
- [PyTorch Documentation](https://pytorch.org/docs/)

---

## Author
**Aswin Arun**  
Final Year Project - Phase 1  
Repository: [github.com/AswinArun7/FinalYr_Proj_Phase1](https://github.com/AswinArun7/FinalYr_Proj_Phase1)

---

## License
This project inherits the AGPL-3.0 license from the original YOLOv5 repository.
