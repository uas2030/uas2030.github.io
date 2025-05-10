---
title: "Report Introduction"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
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

This document outlines the design, development, and strategic approach
of UAS2030 for the SUAS 2025 competition. Building upon our experiences
from SUAS 2024, we have refined our Unmanned Aerial System (UAS) to meet
and exceed the updated requirements set forth in the SUAS 2025 Team
Handbook.

## Mission Requirements and Acceptance Criteria

To achieve a perfect score in the mission demonstration, our UAS must:

- **Complete the mission within 30 minutes**: Ensuring all tasks are
performed efficiently within the allotted time.
- **Operate with a maximum of two operators**: Specifically, a Ground
Control Station (GCS) operator and a safety pilot.
- **Accurately deliver five payloads**: Each payload must be dropped
precisely on designated targets.
- **Maintain high operational excellence**: Demonstrating
professionalism, effective communication, prompt reaction to failures,
and adherence to safety procedures.

## Competition Strategy

Our UAS is engineered to balance system complexity and reliability,
focusing on the following components:

### Airframe and Propulsion
- **Weight:** The fully loaded UAS weighs less than 45 lbs, complying with SUAS 2025 regulations \cite{suas2025handbook}.
- **Endurance:** Capable of flight durations exceeding 30 minutes, accommodating the mission timeline.
- **Cruise Speed:** Maintains an average speed over 66 ft/s to efficiently complete the 15-mile course within 20 minutes.

### Payload Delivery System

- **Mechanism Weight:** The payload release mechanism weighs under 0.25 lbs, minimizing impact on overall weight.
- **Airdrop Altitude:** Payloads are released from altitudes greater than 75 ft, ensuring safety and accuracy.
- **Success Rate:** Designed to achieve a success rate exceeding 95\% in payload delivery.

### Obstacle Detection and Avoidance

- **Detection Range:** Equipped with sensors capable of detecting obstacles over 50 ft away.
- **Sensor Weight:** The obstacle avoidance system weighs less than 0.5 lbs.
- **Power Consumption:** Operates with power consumption under 10 W, preserving overall energy efficiency.

### Communication Systems

- **Range:** Ensures reliable communication over distances greater than 2 km.
- **Uptime:** Achieves approximately 99\% uptime during operations.
- **Power Consumption:** The communication system consumes around 9 W of power.

### Object Detection and Localization (ODLC)

- **Model Accuracy:** Object detection models operate with accuracy exceeding 90\%.
- **Localization Error:** Maintains object localization errors under 20 ft.
- **Power Consumption:** The ODLC subsystem consumes less than 20 W.
- **Subsystem Weight:** Weighs under 10 lbs, ensuring minimal impact on flight performance.

\begin{figure}
    \centering
    \includegraphics[width=0.5\linewidth]{Pic1}
    \caption{Requirements and Acceptance Criteria}
    \label{Requirements and Acceptance Criteria}
\end{figure}
