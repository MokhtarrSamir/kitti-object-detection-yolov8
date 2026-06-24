# KITTI Object Detection with YOLOv8s

Object detection model trained on the KITTI Vision Benchmark Suite to detect and localize multiple object classes in real-world autonomous driving images.

## Problem

Autonomous driving systems require accurate real-time detection of objects in the environment. This project trains a YOLOv8s model to detect 8 object classes from street-level driving images, including cars, pedestrians, cyclists, and trucks.

## Dataset

KITTI Vision Benchmark Suite — 7,481 labeled images captured from a moving vehicle in urban and highway environments.

Object classes: Car, Pedestrian, Van, Cyclist, Truck, Misc, Tram, Person_sitting

## Approach

- Parsed KITTI label format and converted all annotations to YOLO format
- Split data at the image level to ensure balanced class distribution across train, validation, and test sets
- Fine-tuned a pretrained YOLOv8s model using Transfer Learning
- Trained for 35 epochs with automatic augmentation including mosaic, flipping, and color jitter
- Evaluated per-class performance using mAP50 and mAP50-95

## Results

| Class           | mAP50 | mAP50-95 |
|-----------------|-------|----------|
| All             | 0.894 | 0.660    |
| Car             | 0.967 | 0.799    |
| Truck           | 0.970 | 0.829    |
| Tram            | 0.971 | 0.798    |
| Van             | 0.946 | 0.757    |
| Cyclist         | 0.845 | 0.556    |
| Misc            | 0.895 | 0.637    |
| Pedestrian      | 0.821 | 0.491    |
| Person_sitting  | 0.741 | 0.416    |

Weakest class is Person_sitting due to limited training samples (222 instances vs 28,742 for Car).

## Tools

Python, PyTorch, Ultralytics YOLOv8, matplotlib, PIL

## Notebook

Full implementation available on Kaggle including data preprocessing, 
label conversion, training, and visual predictions on test images.
