---
layout: page
title: Projects
excerpt: "Recent Projects"
---

# A few of my projects to date  

## Automated Microscope System

![ams](/images/ams_2.jpg)   

Visiongate had the need to accurately determine target object density in a high viscoisty fluid. To solve this, we dispensed a precise volume of the sample onto a microscope slide (measured by sartorius scale) and then counted the number of objects present. Assuming a homogenous sample, we could then extend this density and infer the total object count. Manually counting target objects (in excess of a thousand per slide) was glacially slow and so I developed a system to scan the microscope slide and then process the images to provide a total count. To produce this product required the fusion of motor control, microscopy, image processing and machinellearning. As the sole engineer, I learned a vast amount regarding component integration, image processing and machine learning techniques.   

![wafers](/images/wafers_9109B_6.jpg)  

### WHAT DID I DO? HOW DID IT PERFORM?
This system is comprised of a precision motorized stage, high resolution monochorome camera, brightfield upright microscope and control computer. To integrate each component for slide imaging I wrote a multi-threaded python control program and C++ image acquisition program. After the slide is imaged, I use python to segment the images by local thresholding and output unclassified target objects. These target objects are then classified by a pre-trained convolution neural network written using tensorflow and trained from approximately 60k images. Segmentation performed with 96-97% accuracy and the object classification performed at ~94% accuracy on a hold-out dataset of ~18k objects. The classifier can distinguish between several cell types, silicon wafers, debris, optical distortions and doubles. A previously used but discarded classifier technique included image processing for feature extraction fed into an unsupervised Density Based Spatial Clustering of Applications with Noise (DBSCAN). 

![ams_img](/images/ams_segmented_imgs.png)  

### CONVOLTIONAL NEURAL NETWOK  
The segmented target object images, captured by the slide scanning microscope, are fed into a convolutional neural network. To further increase classifier performance I added a user specified bias for the target objects that should be allowed, making the assumption of non-contaminated sample. For instance, when imaging "wafers" the user can assume that the slide contains only wafers, double wafers, debris and optical distortions but does not contain any cell types. This bias has been shown to commonly bump performance by 2-4%. 

![cnn](/images/AMS_CNN_model.jpg)  


## Academic Research

### OPTM CARTRIDGE REDESIGN FOR LARGE NEEDLE BIOPSIES
During my senior year of undegraduate studies, I worked in the Human Photonics Labratory (HPL) with Dr. Eric Seibel and Dr. Ronnie Das. While there, I worked on projects focused on Optical Projection Tomography (OPT) Microscopy (OPTM) adapted to large specimen imaging. The device modeled above was designed to be used in a Visiongate, Inc. produced OPT microscope to image large needle biopsies. For more information, see the full [write-up](OPTM Large Specimen Imaging, NAU Presidential Fellowship Writing Example.pdf)  

![exploded](/images/exploded,iso,rendered.jpg)  

![notexplode](/images/iso2,+nr.png)  

![manu](/images/acad_research_optm_cartridge.jpg)  

## UW Remotely Operated Vehicle Team 
Along with several other undergraduates at the University of Washington, I helped found the UW ROV team, which has since been renamed the Underwater Robotics Club, and within this team built a functional submersible with which we participated in the 2015 MATE competition.   

![casus](/images/casus.jpg)  
  
![team](/images/casus_team.jpg)  

My personal contributions to the team revolved around the ideation, design and manufacturing of the pneumatic manipulator and thurster mounts, seen below.   

![manipulator](/images/ROV_gripper1.jpg)  

![thruster mounts](/images/gripper+thursters1.jpg)  