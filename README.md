Installation and Usage Instructions
1. Environment Setup

Ensure you have Python 3.8+ installed.

Install the required packages using pip:

pip install numpy opencv-python matplotlib scikit-learn torch torchvision timm


Note: timm is required for the Swin Transformer implementation.

(Optional) If using Jupyter Notebook:

pip install notebook

2. Data Preparation

Upload your UAV video footage or frames to the working directory.

Ensure videos are in .mp4 or .avi format and frames/images are in .jpg or .png format.

3. Pipeline Overview

The system executes the following processing steps automatically:

Video Frame Division:

The input video is split into individual frames for sequential analysis.

Foreground Enhancement:

Bilateral filtering is applied to improve the visibility of moving objects (humans) while reducing background noise.

Grayscale Conversion:

Frames are converted from RGB to grayscale to simplify subsequent computations.

Human Detection & Skeleton Extraction:

Convolutional Neural Networks (CNNs) detect humans and segment their skeletons for feature extraction.

Feature Extraction:
The system computes multiple features from skeleton and image data:

Joint angles

Linear displacements

Velocities of joints

Fiducial points (keypoints on human body)

Geodesic distances

Histograms of Oriented Gradients (HOG)

Feature Optimization:

Linear Discriminant Analysis (LDA) is applied to reduce feature dimensionality and improve discriminative power.

Classification:

Optimized features are classified using the Swin Transformer, which learns spatio-temporal patterns for gesture recognition.
