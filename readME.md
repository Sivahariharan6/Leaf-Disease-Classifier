## Leaf-Disease-Classifier

* Leaf Disease Classifier classifies disease based on image processing techniques for automated vision system used at agricultural field. 
* The classifier is trained on the dataset found at :
      * https://www.kaggle.com/emmarex/plantdisease
      * https://github.com/spMohanty/PlantVillage-Dataset
      
  *dataset images*

# Table of content
- [Disease Classifier](#classifierInfo)
- [Installation](#installation)

## Disease Classifier

The whole disease classification process is divided into 3 stages as in 

*block diagram here*

- An input image is initially taken, A You Only Look Once (YOLOv3), object detector is run over the input image to obtain the coordinates of bounding boxes around leaves present in the image if any. The detector divides the input image into a grid and then analyzes every cell to identify features of the target object. The adjacent cells where the features are detected with high confidence are then put together to produce the output of the model.

*o/p yolo here*
    
- The leaves are then cropped out of the image using the OpenCV library using the given coordinates from the bounding boxes. These extracted images are passed as input to a CNN Classifier which classifies the input into the 8 classes of plants from the dataset. 

*flow chart image main classifier----->sub-classes
    
- 8 CNN classifiers are trained to identify the diseases of each of the 8 plant classes.  The result from stage 2 is used to call the classifier that has been trained to classify the different diseases for that plant. If there are none, the leaf would be classified as 'Healthy'.

- All the above CNN's are trained on ResNet-50 Architecture using "Transfer Learning" from the ImageNet weights.

## Installation
