# Face Detection Techniques
Face detection algorithms using Haarcascade, HOG (Histograms of Oriented Gradients) and CNN

# User Notes
This notebook was originally executed in Google collab for which the data/library importing might differ in other environments.
This notebook serves as an introductory approach to different face detection techniques: Haarcascade, HOG and CNN.

# Haarcascade
Haarcascade runs different orientations of black and white filters that runs across pixels of an image in a sliding window manner and then produces an matrix array producing values of (sum of white pixels- sum of black pixels) where each value of the matrix represents calculation of running one single filter across whole image. During training the algorithm detects the patterns that extracts the feature of a face (look into AdaBoost algorithm, a.k.a Adaptive Boosting). 

The reason it is called cascade is because the image runs through a series of classifiers where each classifier detects certain pattern in the image, if the first classifier detects its assigned pattern within the image, it passes on the image to the next classifier with its corresponding pattern check all the way towards the last classifier. If one of the classifier fails to detect, the system exits the classifier chain and comes out as no detection.

# HOG (Histogram of Oriented Gradients)
This algorithm looks for color gradients and gradient vector (i.e. direction in which the gradient increases). For example: a yellow shirt person on a gray road background will have high gradient variation towards the edge of the yellow shirt and his skin.  HOG produces two matrix: the gradient magnitude and  gradient direction (aka angle towards magnitude change). Both of them matrixes are used in a histogram where x-axis is the gradient direction value while the y-axis represent the corresponding gradient magnitude. 


