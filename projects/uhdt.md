---
layout: project
type: project
image: img/uhdt_logo_1.png
title: "University of Hawaii Drone Technologies"
date: 2024
published: true
labels:
  - Engineering
  - Drones
summary: "A text adventure game that I developed for ICS 313."
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ff6pcmQL3Yw?si=dQCnSHlVUW-q0Qq4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

 

<hr>
The University of Hawaii Drone Technologies (UHDT) team is one of the many Vertically Integrated Project (VIP) teams within the College of Engineering at the University of Hawaii at Manoa. As a multidisciplinary team, UHDT brings together students from various engineering disciplines, including Electrical, Mechanical, Computer, and Civil Engineering. The team is open to students of all levels, from freshmen to seniors, providing a collaborative environment where members can gain hands-on experience in drone design, development, and implementation.
 
The objective of the UHDT initiative is to develop an autonomous Unmanned Aerial System (UAS), an autonomous Air Delivery System, and an autonomous Image Processing System capable of accurately delivering payloads to designated ground targets.  This initiative aligns with the regulations set forth for the 2025 SUAS Competition and is part of an internal Game of Drones competition, providing students with opportunities to apply their skills in autonomous navigation, control systems, and computer vision while adhering to real-world industry and competition standards. The competition 
  
The mission begins with Mission Preparation, where the Ground Control System (GCS) receives GPS coordinates, generates waypoints, and loads strobing beacon payloads into the drone. Following this, the Takeoff phase occurs, where the drone lifts off either autonomously or manually. Once airborne, the drone embarks on a three-mile Waypoint Lap, flying at top speed to reach the Search Area. Upon arrival, the drone reduces speed and hovers at 75 feet, scanning the ground to identify targets such as vehicles, trash cans, or umbrellas.

The team is divided into four key subsystems: hardware, software, air delivery, and image processing (IP). I am part of the image processing (IP) subsystem, which focuses on utilizing computer vision to detect and classify targets. The process begins by collecting data from the camera and drone sensors (including yaw, altitude, and GPS), which is then transmitted to the onboard computer, the NVIDIA Jetson Orin Nano. Once received, the Jetson Orin Nano processes the input data and feeds the images into an Object Detection and Classification (ODCL) system powered by YOLOv8, a machine learning model for real-time object detection. This system is responsible for identifying and categorizing targets based on the captured imagery. After detection, the identified targets undergo Optimized Payload Matching, ensuring that the appropriate payload is assigned and deployed based on the target’s characteristics. At the same time, the system performs Georeferencing and Duplicate Removal using tools like PyProj, which accurately maps target locations and eliminates redundant detections. The final output is a precise and optimized target map, enabling the drone to execute autonomous payload delivery with high accuracy and efficiency.

As a member of the IP subsystem, my primary contributions have been focused on training machine learning models and developing the georeferencing script. Training the models begins with curating a high-quality dataset. To do this, we utilize Roboflow and its extensive collection of publicly available datasets. However, since these datasets are created by the general public, they often contain low-quality or irrelevant images, which can negatively impact model performance. To address this, we carefully filter out unwanted images to ensure that only high-quality data is used for training. Once the dataset is refined, we use these images to generate test datasets to evaluate the model’s accuracy. This process is repeated iteratively, refining the dataset and retraining the model until we achieve a reasonable accuracy threshold (>90%). In addition to model training, I have also worked on the georeferencing script, which calculates the global coordinates of detected targets. This is achieved by using the drone’s position, yaw (orientation), and the detected target’s position within the image. The drone then navigates to these coordinates to drop the payload.
<hr>
