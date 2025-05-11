---
title: "Object Detection, Localisation, and Classification"
description: ""
summary: ""
date: 2023-09-07T16:13:18+02:00
lastmod: 2023-09-07T16:13:18+02:00
draft: false
weight: 910
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---


The Object Detection, Localisation, and Classification (ODLC) subsystem is built around neural network pipeline optimised for real-time performance and accuracy.
The pipeline begins with a YOLOv11 model tasked with initial target detection and classification.

This design ensures robust classification performance while maintaining real-time throughput.
All detected targets are compiled into a unified output that includes target location, shape, shape colour, and alphanumeric character with its colour.

To accelerate model training, the team adopted an automated data synthesis approach using Blender, where target objects were rendered on top of UAV-captured aerial backgrounds.

Similar to last year's approach, the team adopted an automated data synthesis approach using [Project AirSim](https://github.com/microsoft/AirSim) to generate photorealistic training images.
A 3D model from each object class is overlaid randomly over the scene, without overlap.
Each rendered image was automatically annotated in compliance with the dataset requirements for target size, pose, and color variation.
This process significantly reduced human effort and improved dataset diversity and quality.

Around 12,000 synthetic and real composite images were generated and used for training and validation.
The dataset underwent extensive augmentation—incorporating noise, transformations, and lighting changes—to simulate real-world variability.
As a trade of for performance, we reduce the input image size to the model which hampers the model's ability to detect smaller objects as shown in \ref{fig:ai-confusion}.
Consequently, performance testing showed that the primary model operates at 32 FPS on the onboard Jetson Orin NX and achieves a high mean Average Precision (mAP) across all classification categories except bats.
\ref{fig:valid-results} summarises the data generation and training process.

<div class="row text-center justify-content-center">
	{{< figure  
	src="odlc-confusion.jpeg"
	width="128"
	alt="A confusion matrix for the YOLOv11 model"
	title="A confusion matrix for the YOLOv11 modely"
	caption="A confusion matrix for the YOLOv11 model"
	 >}}
	{{< figure  
	src="odlc-metrics.jpeg"
	width="128"
	alt="A confusion matrix for the YOLOv11 model"
	title="YOLOv11 model metrics"
	caption="YOLOv11 model metrics"
	 >}}
</div>

Through extensive field and software testing, the system proved its reliability, consistently achieving accurate ODLC predictions under a variety of flight and weather conditions.
