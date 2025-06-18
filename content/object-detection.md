---
title: Object Detection Pipeline using ResNet18
date: 2025-06-17
---


This repository demonstrates a simple visual inspection pipeline using a pretrained CNN. Images are loaded into the system, and then the CNN detects objects within the image. The script creates copies of the images, labeled with the predicted class and confidence outputs. The script also logs all of the results in a csv file for later inspection.

## Prerequisites

- [Python](/python)
- A python venv to download the packages for this code
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
- Change the model used in `model.py` to anything you want. Just remember that the ResNet18 labels are used in both `model.py` and `look.py` to label the predicted classes.
- Add images to the `images/` folder to process. All images must be `.png`, `.jpg`, or `.jpeg`.

Running
- `python look.py`

Outputs
- The `outputs/` folder doesn't automatically clear between runs, so manually clear the outputs folder if you are re-running.
- Copies of all the images from `images/` labeled with predicted class and confidence levels
- A csv log of the image name, predicted class, and confidence level, stored as `inspection_log.csv`

## Results

**Example: `screws.jpg`** (input on left, output on right)
<div style="display: flex; gap: 10px;">
  <img src="/img/screws.jpg" alt="Before" width="300"/>
  <img src="/img/screws-labeled.jpg" alt="After" width="300"/>
</div>

**Example: `broken-bottle.jpg`** (input on left, output on right)
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
- Loads ResNet18, a CNN pretrained on ImageNet.
	- a pretrained CNN from the PyTorch library.

**`look.py`**
- Loads the model defined in `model.py`
- Runs a loop to process each individual image from `images`/
- For each file in `images/`:
	- Opens the image and transforms it into a tensor
	- Uses PyTorch to run the image through the previously defined model with no training
	- The model outputs the predicted class and the confidence value for the highest confidence prediction
	- OpenCV puts text over a copy of the image and saves the new image to the `outputs/` folder.
	- A new line with the results is appended to the `inspection_log.csv`

**Further extensions could include:**
- Confidence thresholding at e.g. 0.5 to prevent bad detections.
- Replacing ResNet18 with a different model.
- Real-time video input using OpenCV and a video stream.