<h1>Dexterity</h1>


Sign Languages are a set of languages that use predefined actions and movements to convey a message. These languages are primarily developed to aid deaf and other verbally challenged people. They use a simultaneous and precise combination of movement of hands, orientation of hands, hand shapes etc. Different regions have different sign languages like American Sign Language, Indian Sign Language etc. We focus on Indian Sign language in this project.

Indian Sign Language (ISL) is a sign language that is predominantly used in South Asian countries. It is sometimes referred to as Indo-Pakistani Sign Language (IPSL). There are many special features present in ISL that distinguish it from other Sign Languages. Features like Number Signs, Family Relationship, use of space etc. are crucial features of ISL. Also, ISL does not have any temporal inflection.

In this project, we aim towards analyzing and recognizing various alphabets from a database of sign images. Database consists of various images with each image clicked in different light condition with different hand orientation. With such a divergent data set, we are able to train our system to good levels and thus obtain good results.

We investigate different machine learning techniques like Support Vector Machines (SVM), Logistic Regression, K-nearest neighbors (KNN) and a neural network technique Convolution Neural Networks (CNN) for detection of sign language




 <h2>Image Preprocessing</h2>

 <h3>Segmentation:</h3>
The main objective of the segmentation phase is to remove the background and noises, leaving only the Region of Interest (ROI), which is the only useful information in the image. This is achieved via Skin Masking defining the threshold on RGB schema and then converting RGB colour space to grey scale image. Finally Canny Edge technique is employed to identify and detect the presence of sharp discontinuities in an image, thereby detecting the edges of the figure in focus.  

  
<h3>Feature Extraction:</h3>
The Oriented FAST and rotated BRIEF (ORB) technique is used to extract descriptors from the segmented hand gesture images. ORB is a novel feature extraction method which is robust against rotation, scaling, occlusion and variation in viewpoint.

<h2> Classification</h2>
The ORB descriptors extracted from each image are different in number with the same dimension (64). However, a multiclass SVM requires uniform dimensions of feature vector as its input. Bag of Features (BoF) is therefore implemented to represent the features in histogram of visual vocabulary rather than the features as proposed. The descriptors extracted are first quantized into 150 clusters using K-means clustering. Given a set of descriptors, where K-means clustering categorizes numbers of descriptors into K numbers of cluster center.

The clustered features then form the visual vocabulary where each feature corresponds to an individual sign language gesture. With the visual vocabulary, each image is represented by the frequency of occurrence of all clustered features. BoF represents each image as a histogram of features, in this case the histogram of 24 classes of sign languages gestures. 

 <h2>Bag of Features model</h2

Following Steps are followed to achieve this:

* The descriptors extracted are first clustered into 150 clusters using K-Means clustering.

* K-means clustering technique categorizes m numbers of descriptors into x number of cluster centre.

* The clustered features form the basis for histogram i-e each image is represented by frequency of occurrence of all clustered features.

* BoF represents each image as a histogram of features, in our case the histogram of 24 classes of sign language is generated.

<h2 Classifiers</h2

After obtaining the bag of features model, we are set to predict results for new raw images to test our model. Following classifiers are used :
+ Naive Bayes
+ Logistic Regression classifier
+ K-Nearest Neighbours
+ Support Vector Machines
+ Convolution Neaural Network

