# Face-Mask-Detection
#### This project involves developing a face mask detection system using MobileNet and CNN.

## Objective:
#### The aim is to build a classification model based on face mask detection involving two classes: 'mask' and 'no mask. The model involves training pictures of images with people wearing masks and people not wearing masks.

## Dataset:
Link: https://github.com/prajnasb/observations/tree/master/mask_classifier 
<br />
The dataset was built by prajnasb and was acquired from her GitHub Repo.
<br />
The dataset was built by collecting images of people's faces and artifically occulding the lower face with a picture of a mask. The mask is occulded over the lower face by estimating the landmarks of the lower face and artificially applying the mask image.

## Packages and Dependancies:
* Python 3.8
* numpy
* seaborn
* imutils
* OpenCV
* tensorflow
* keras
* sklearn

##### The rest of the dependancies are listed in the requirements.txt file. It can be installed from the command line using 'pip'


## Training:
* The training comprises of two parts. The pre-trained MobileNetV2 and a custom fully connected network as the head of the network.
* The mobilenetv2 network is trained on the famous Imagenet dataset. The head of the network is removed, and the custom made fully connected layer is appended to it.
* 20% of the dataset is used for the validation set.
* Prior to training, the data was augmented by tweaking the rotation range, zoom range, horizontal flip and more.
* The results of the training was as desired and the network performed fairly well.

## Preprocessing:
* The first step to the process is face detection. The face detection is done using a pre-trained SSD resnet caffe model and prototxt config file.
* A threshold for confidence of the detection is set, above which if the detection obtains, that detection is considered.
* The method involves looping through the frames of the video and resize the frame accordingly.
* A image is converted to a blob object which is caffe-model-compatible. The blob is trained on the network and detections are returned. 
* Then, the detections are looped over and the bounding box coordinates of the faces with the confidence above the threshold is obtained.
* The faces are then obtained to predict if the face has a mask or not.

## Metrics:
* **Performance**: Accuracy, Classification Report
* **Loss**: Binary Cross Entropy
* **Optimizer**: Adam

## Performance:
* **Training Accuracy**: 99.63%
* **Traning Loss**: 0.0091
* **Validation Accuracy**: 98.91%
* **Validation Loss**: 0.0147





## References:
* https://github.com/prajnasb/observations/tree/master/mask_classifier
* https://www.pyimagesearch.com/2020/05/04/covid-19-face-mask-detector-with-opencv-keras-tensorflow-and-deep-learning/
