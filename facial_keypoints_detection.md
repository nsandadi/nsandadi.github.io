## Facial Keypoints Detection

### Project description: 
The objective of this task is to predict keypoint positions on face images. Detecing facial keypoints is a very challenging problem.  
Facial features vary greatly from one individual to another, and even for a single individual, there is a large amount of variation due to 3D pose, size, position, viewing angle, and illumination conditions. Computer vision research has come a long way in addressing these difficulties, but there remain many opportunities for improvement.

There are 15 key points for facial detection and the overall training data contains 7049 images. The images are 96x96 pixels.Testing data contains 1783 images.

Packages Used 
- Keras
- Sklearn
- Pandas
- Numpy
- Matplotlib

Environment: Google Colab (GPU)

### Challenges:
There are 2140 training records that have missing values. Since only 30% of training images had all 15 facial keypoints, data augmentation was an effective way to increase the number of training examples without leading to overfitting.
Deep learning models in general are data greedy and the performance of the models suffer when testing images vary a lot from training images. Thus, data augmentation became an essential technique to capitalize on the limited number of training images.

However, there are a few challenges that come with augmentation:
- Augmentation could increase the number of training images substantially which could raise a storage problem. Keras has a powerful API called ImageDataGenerator that resolves this problem. The generator can generate augmented images from the training images on the fly.
- Another challenge specific to facial keypoint detection is that the target values or landmarks also needs to change when an image is translated, (i.e.), if the image of a face is shifted by 3 pixels, the landmark coordinates of the eye, nose, etc. also need to be shifted.

###[Project Report](/pdf/w207_Facial_Keypt_Detection.pdf)

