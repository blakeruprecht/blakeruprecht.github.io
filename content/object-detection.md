---
title: Object Detection Pipeline using ResNet18
date: 2025-06-18
---
[GitHub Repo: object-detection](https://github.com/blakeruprecht/object-detection) 

This project demonstrates a simple visual inspection pipeline using a pretrained convolutional neural network (CNN). Images are loaded and passed into the CNN model, which outputs a predicted class and confidence score. The class and score are then overlaid on each image using OpenCV, and saved for further inspection. All of the results are logged to a CSV file.

## Prerequisites

- [github.com/blakeruprecht/object-detection](https://github.com/blakeruprecht/object-detection)
- [Python](/python)
- Virtual environment (recommended):
	- `python3 -m venv venv`
	- `source venv/bin/activate`
	- `pip install torch torchvision opencv-python matplotlib`

## System Overview

- `compvis/`
	- `images/`
		- `example1.png`
		- `example2.jpg`
	- `outputs/`
		- `example1.png`
		- `example2.jpg`
		- `inspection_log.csv`
	- `model.py`
	- `look.py`

## Workflow
Inputs
- Add `.png`, `.jpg`, or `.jpeg` images to the `images/` folder.
- Change the model used in `model.py` to anything you want. Just remember that the ResNet18 labels are used in both `model.py` and `look.py` to label the predicted classes.
- Swap out the model in `model.py`. By default, `model.py` and `look.py` use ResNet18 with ImageNet labels.

Running
- `python look.py`

Outputs
- Images labeled with class and score saved to `outputs/`
- Results logged in `outputs/inspection_log.csv`
- Note: `outputs/` doesn't get cleared between runs.

## Results

**Example: `screws.jpg`**, Input (left) → Output (right)
<div style="display: flex; gap: 10px;">
  <img src="/img/screws.jpg" alt="Before" width="300"/>
  <img src="/img/screws-labeled.jpg" alt="After" width="300"/>
</div>

**Example: `broken-bottle.jpg`**, Input (left) → Output (right)
<div style="display: flex; gap: 10px;">
  <img src="/img/broken-bottle.jpg" alt="Before" width="300"/>
  <img src="/img/broken-bottle-labeled.jpg" alt="After" width="300"/>
</div>

**Example of the output log**: `inspection_log.csv`
```
filename,predicted_class,confidence
broken-bottle.jpg,chocolate sauce,0.4199
pill-blister-packs-boken.jpg,pencil sharpener,0.2043
broken-cable.jpg,whistle,0.1151
circuit-components.jpg,lighter,0.2302
bolt-failure.png,screw,0.9955
pills-blister-pack.jpg,remote control,0.5651
random-weird-nuts.jpg,dumbbell,0.8688
plug-on-fire.jpg,spotlight,0.2793
screws.jpg,screw,0.9930
bottle-conveyor.jpg,cleaver,0.4906
```


## Code Walkthrough

**`model.py`**
- Loads ResNet18, a CNN pretrained on ImageNet, from `torchvision.models`
- Applies the models corresponding image transform

**`look.py`**
- Loads the model and transform defined in `model.py`
- Iterates through all files in `images`/
- For each .png/.jpg/.jpeg in `images/`:
	- Opens the image and transforms it
	- Runs the image through the PyTorch inference model
	- Predicts the class and confidence score of the class
	- Overlays the class and score over a copy of the original image using OpenCV
	- Saves the annotated image to `outputs/`
	- Appends the result to `outputs/inspection_log.csv`

## Next Ideas
- Confidence thresholding (e.g. 0.5 to prevent bad detections)
- Replacing ResNet18 with a different model.
- Real-time video input using OpenCV and a video stream.