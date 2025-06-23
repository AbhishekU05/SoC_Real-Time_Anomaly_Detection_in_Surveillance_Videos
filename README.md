# Real-Time Anomaly Detection in Surveillance Videos

In this SoC, I have learnt how to use YOLOv5 for object detection and object tracking. The .ipynb file in the repo contains the week 3 assignment in which I have used YOLOv5 to detect pedestrians in a video. The implementation uses the MOT17 dataset.

The MOT17 dataset is a benchmark dataset used in the Multiple Object Tracking (MOT) research community. It is part of the MOTChallenge, which provides a standard for evaluating and comparing tracking algorithms.

The MOT17 (Multiple Object Tracking 2017) dataset is designed to evaluate pedestrian tracking algorithms in real-world scenarios. It includes multiple video sequences with varying challenges such as:

*   Camera motion (static and moving)
*   Occlusions
*   Crowded scenes
*   Varying lighting and weather conditions

In the implementation, I have used 2 models, YOLOv5s and YOLOv5m. I have also frozen a few layers in the medium model and compared the results of all the three models. 

### YOLOv5 Model Performance Comparison on MOT Dataset

| Model Variant         | Frozen Layers | Precision (P) | Recall (R) | mAP@0.5 | mAP@0.5:0.95 |
|-----------------------|----------------|---------------|------------|---------|--------------|
| YOLOv5s               | No           | 0.680         | 0.410      | 0.540   | 0.270        |
| YOLOv5m               | No           | 0.720         | 0.490      | 0.600   | 0.313        |
| YOLOv5m               | Yes          | **0.747**     | **0.596**  | **0.707** | **0.361**    |


- YOLOv5m outperforms YOLOv5s on all metrics, as expected due to its larger capacity.
- Freezing layers in YOLOv5m leads to the best overall results, especially in Recall and mAP, suggesting better transfer learning from pretrained weights on the MOT dataset.
