# Keypoint-Detection-Using-Movenet-Model
MoveNet is a state-of-the-art model developed by Google for human pose detection, capable of identifying 17 keypoints on the human body. It is designed for real-time applications, offering two variants: Lightning and Thunder. The Lightning model is optimized for low-latency scenarios, while Thunder is tailored for high-accuracy tasks. Both models can achieve over 30 frames per second, making them suitable for live applications such as fitness tracking and sports analytics.

### Architecture and Functionality

MoveNet employs a bottom-up approach for keypoint detection, utilizing heatmaps to accurately localize body parts. The architecture includes:

- **Feature Extractor**: Based on MobileNetV2, it generates a semantically rich feature map.
- **Prediction Heads**: Four heads are used to predict the geometric center and the full set of keypoints.

The model follows a series of steps to process input images:

1. **Center Detection**: Identifies the center of individuals in the frame using a person center heatmap.
2. **Initial Keypoint Regression**: Generates an initial set of keypoints based on the center.
3. **Weight Adjustment**: Adjusts keypoint predictions based on their proximity to the center to filter out background noise.
4. **Final Keypoint Selection**: Retrieves the coordinates of the maximum values in the heatmap for each keypoint channel, refining the predictions[1][2][3].

### Applications

MoveNet is versatile and can be applied in various fields, including:

- **Fitness and Sports**: Real-time feedback for exercise form and performance.
- **Augmented Reality**: Enhancing user interaction through pose recognition.
- **Surveillance**: Monitoring movements and behaviors in security contexts[3].

### Implementation

To implement MoveNet for pose detection, TensorFlow.js has been used in the given colab notebook for ease of running.

### Dataset used 
The VITON-HD (High-Resolution VITON-Zalando Dataset) is a dataset for high-resolution (1024x768) virtual try-on of clothing items. It consists of 13,679 frontal-view woman and top clothing image pairs. The model has been trained on this dataset.

VITON-HD was introduced in the CVPR 2021 paper "VITON-HD: High-Resolution Virtual Try-On via Misalignment-Aware Normalization". The authors proposed a novel virtual try-on method called VITON-HD that successfully synthesizes 1024x768 virtual try-on images by handling misaligned areas and preserving input details.
