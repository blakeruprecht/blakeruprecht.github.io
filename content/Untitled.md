

## Prerequisites
Assuming that you already have Python installed, create a new virutal environment for this project (or use one you already have) and install the required Python packages to run this code.
- `pip install torch torchvision opencv-python matplotlib`



That’s expected—ResNet18 pretrained on ImageNet isn’t trained to detect screws or defects specifically. The goal here was to show you can run the full pipeline end-to-end with images, annotations, and logging.

If you want to push it closer to a real inspection system, the next step is to train or fine-tune a model on labeled images from your domain (e.g., screws, bolts, defects).

For your technical writing sample, this demo shows you understand:
- Model loading and preprocessing
- Image processing and annotation
- Logging outputs
- Organizing code and results


### Abstract

This project demonstrates a simplified visual inspection pipeline using a pretrained convolutional neural network (CNN). The system classifies product images, overlays predicted labels, logs results, and simulates offline inspection and data capture. This kind of workflow mirrors foundational patterns in industrial computer vision: high-throughput analysis, process logging, and model-driven adaptation.

---
### **1. System Overview**

This prototype mimics Boulder Imaging’s Vision Inspector pipeline at a conceptual level:
- A **ResNet18 CNN** classifies input images.
- **OpenCV** handles image I/O and annotation.
- **Python scripting** processes a batch of images and logs structured output.
- The system produces:
    - Annotated inspection results (image overlays)
    - A CSV inspection log (filename, predicted class, confidence)        
    - A modular pipeline extensible for online/offline inspection

While the model used is pretrained on ImageNet, the structure supports fine-tuning or replacement with domain-specific architectures.

While the model is trained on ResNet18 CNN, the structure supports fine-tuning or replacement with domain-specific architectures.

---
### **2. Setup Instructions**

Clone the repository and set up a Python environment:
`git clone {your repo}`
`cd compvis-inspector`
`python3 -m venv venv`
`source venv/bin/activate`
`pip install torch torchvision opencv-python matplotlib`

Place `.jpg` or `.png` product images into the `images/` folder. Then run:
`python look.py`
Results will appear in `outputs/`.

---
### **3. Code Walkthrough**

#### a. Load Model & Transform

Using `torchvision.models.resnet18(weights=ResNet18_Weights.DEFAULT)`, we load a pretrained CNN and use the matching transformation pipeline to normalize input images for inference.

#### b. Batch Processing

We iterate over files in `images/`, applying the transform and passing each image through the model. We extract the highest-probability class and confidence score.

#### c. Visual Feedback

We use OpenCV to overlay the prediction directly on the image for fast human-in-the-loop verification. This simulates real-time display of classification results on-screen.

#### d. Logging

Each inference is written to a CSV file for later filtering, sorting, and analysis—mirroring the logging/auditing layer of many vision systems.

---
### **4. Sample Results**

_Show a screenshot of one or two annotated images from the `outputs/` folder here._  
_You can also paste a few lines from `inspection_log.csv`._

---
### **5. Conclusion**

This project showcases a minimal working version of an industrial inspection pipeline. Though pretrained on ImageNet and not domain-specific, it demonstrates core system behavior:

- Fast, automated classification
- Visual overlay of results
- Structured result logging
- Extensible Python-based implementation

Further extensions could include:
- Confidence thresholding to flag potential defects
- Retraining on custom data
- Real-time video input (e.g. OpenCV + webcam stream)
- Integration with an offline “Studio” tool for simulation, replay, and recipe development