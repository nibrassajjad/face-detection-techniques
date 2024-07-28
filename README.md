# Face Detection Techniques
Face detection algorithms using Haarcascade, HOG (Histograms of Oriented Gradients), and CNN.

![image](https://github.com/user-attachments/assets/435ea468-d8da-4eeb-9932-9446aac5853c)

# User Notes
This notebook was originally executed in Google Colab, so the data/library importing might differ in other environments. This notebook serves as an introductory approach to different face detection techniques: Haarcascade, HOG, and CNN.

# Haarcascade
Haarcascade classifiers use features similar to convolutional kernels, known as Haar-like features, to detect objects in images. These features capture visual characteristics such as edges, lines, and textures by computing the difference between the sum of pixel intensities in adjacent rectangular regions.

During training, the AdaBoost algorithm (Adaptive Boosting) selects a small number of critical features from a large set of potential features. These selected features are then organized into a cascade of classifiers. Each classifier in the cascade is a simple decision tree that looks for specific features.

The term "cascade" refers to the sequential application of these classifiers. The image is processed through each classifier in turn:
1. **Initial Classifier**: If the first classifier detects its assigned feature, the image region is passed to the next classifier.
2. **Subsequent Classifiers**: Each subsequent classifier performs a similar check.
3. **Decision**: If any classifier in the sequence rejects the image region, the detection process stops for that region. Only if all classifiers in the cascade approve the region is it considered to contain a face.

This cascading process allows the system to quickly discard non-face regions, which significantly speeds up the detection process.

# HOG (Histogram of Oriented Gradients)
The HOG algorithm is used for object detection by analyzing the gradients in an image to capture the shape and structure of objects. It is particularly effective for detecting humans.

1. **Gradient Calculation**: The first step is to compute the gradients of the image using gradient operators (like the Sobel operator) to produce gradient values in both the horizontal and vertical directions.

2. **Gradient Magnitude and Direction**: For each pixel, the gradient magnitude (indicating the strength of the change in intensity) and the gradient direction (indicating the angle of the change) are computed.

3. **Spatial Binning**: The image is divided into small regions called cells, and a histogram of gradient directions is compiled for each cell. The gradients are weighted by their magnitude, so stronger gradients contribute more to the histogram.

4. **Normalization**: To account for variations in lighting and contrast, the histograms of gradient directions in each cell are normalized by grouping cells into larger blocks and normalizing the histograms within each block. This step makes the descriptor more invariant to changes in illumination and shadowing.

5. **Descriptor Vector**: The normalized histograms from all the blocks are concatenated to form a single feature vector, which represents the entire image. This feature vector can then be used in a machine learning algorithm to classify the image or detect objects.

The HOG descriptor captures the edge structure of objects and is effective in distinguishing different shapes and patterns within an image.

# CNN (Convolutional Neural Network)
Convolutional Neural Networks (CNNs) are a class of deep learning models that are particularly effective for image recognition and classification tasks. CNNs can automatically learn and extract features from images, making them highly suitable for face detection.

In this project, we used a pre-trained CNN model for face detection, specifically the dlib library's mmod_human_face_detector.dat model, which is designed to detect human faces in images.

