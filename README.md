# SAM3-VLM Modular Pipeline

A modular real-time multimodal perception pipeline combining:

-  **SAM3** (Segment Anything Model) for object segmentation  
-  **Qwen3-VL** for visual-language reasoning  
-  Stable mask ID selection  
-  Pixel centroid extraction for robotics integration  

---

## Overview

This project implements a clean and modular architecture:

Input Image
↓
SAM3 Segmentation
↓
Labeled Overlay (ID:0, ID:1, ...)
↓
Qwen3-VL Reasoning
↓
Mask ID Selection
↓
Centroid Extraction

The system is designed for:

- Real-time streaming
- Robotics pick-and-place pipelines
- Multimodal AI research
- Modular AI system design

---

##  Architecture

### Module A – Segmentation
Uses **Ultralytics SAM3** to generate object masks from bounding box prompts.

### Module B – Labeled Overlay
Creates a single overlay image with stable mask IDs.

### Module C – VLM Selection
Qwen3-VL identifies which segment corresponds to a target object.

### Module D – Centroid Extraction
Extracts pixel centroid for downstream robotics use.

---

## Project Structure
.
├── main.py
├── sam_stream_overlay/
├── README.md
└── requirements.txt

---
## Example Output
Labeled overlay saved: sam_stream_overlay/frame_0001.jpg
VLM: id=1 | chosen mask_id: 1
Centroid pixel: (412.3, 287.9)


## 🛠 Installation

### Clone the repository

```bash
git clone https://github.com/yourusername/SAM3-VLM-modular-pipeline.git
cd SAM3-VLM-modular-pipeline
pip install ultralytics torch opencv-python numpy ollama


