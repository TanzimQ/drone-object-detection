# Drone Object Detection — Antlings Technical Assessment

Human and car detection system using YOLOv8 trained on VisDrone dataset.

## Dataset
- VisDrone2019-DET (YOLO format)
- 6,471 training images, 548 validation images
- 10 classes: pedestrian, people, bicycle, car, van, truck, tricycle, awning-tricycle, bus, motor

## Model
- YOLOv8s fine-tuned on VisDrone
- Optimizer: AdamW | Epochs: 30 | Image size: 640x640
- Built-in augmentations: mosaic, HSV shifts, flipping, scaling, random erasing

## Results
| Metric | Value |
|--------|-------|
| mAP50 | 0.371 |
| mAP50-95 | 0.215 |
| Precision | 0.496 |
| Recall | 0.383 |
| Car mAP50 | 0.775 |
| Pedestrian mAP50 | 0.402 |

## Per Class Results
| Class | mAP50 |
|-------|-------|
| Car | 0.775 |
| Bus | 0.532 |
| Van | 0.429 |
| Motor | 0.416 |
| Pedestrian | 0.402 |
| People | 0.292 |
| Truck | 0.355 |
| Bicycle | 0.118 |

## Inference Results
- Average humans detected per image: 22.3
- Average cars detected per image: 9.0

## Key Observations
- Humans appear extremely small (10-30px) due to aerial viewpoint
- Heavy occlusion in crowded scenes
- Cars are easier to detect than humans due to larger size
- YOLOv8 built-in augmentations handle preprocessing automatically

## Strengths
- Strong car detection (mAP50 0.775)
- Fast inference (~2.6ms per image)


## Limitations
- Small objects (bicycle, tricycle) harder to detect
- Heavy occlusion reduces recall
- Dense crowd scenarios reduce accuracy


Kaggle Notebook link - https://www.kaggle.com/code/mdtanzimqaiyum/drone-object-detection 
