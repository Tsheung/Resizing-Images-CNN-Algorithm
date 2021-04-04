# Resizing-Images-CNN-Algorithm
Examining Resizing Images with a CNN Algorithm and its Accuracy 

## Description
When using CNN algorithms with input images, the proprocessing technique of resizing images tend to be an experimental task. Images in complex datasets are often not the same sizes. In an attempt to analyze the best way to resize images, this experiment uses two datasets: one with a default image size and another dataset without a preset size. The study explores how the CNN testing accuracy may be affected by how the image is resized smaller and larger. The results show that images that are resized smaller and closer to the default or average size has similar accuracy than the larger images. Larger resized images tend to overfit and have lower accuracies and higher loss.

## Datasets
- Cifar-10 dataset:
  - 60,000 colored images within 10 classes  
  - Each class contains 6,000 images
  - 32 x 32 
- Natural Images: 
  - 6,899 colored images within 8 classes
  - No default image dimension


## CNN Architecture
Image (Chosen Size) → Convolutional Layer (Filters : 32,Kernel : 3x3) → ReLu Activation → Max Pooling (2x2) → Convolutional Layer2(Filters : 64,Kernel : 3x3) → ReLu Activation → Max Pooling (2x2) → Flatten → Fully Connected Layer1(64outputs) → ReLu Activation → Dropout Layer (Rate : 0.5) → Fully Connected Layer(10outputs) → Softmax Activation → Cross−Entropy Loss Function

## Experiment 1
The 8-layer CNN architecture was used to compare the training and testing accuracies of varying image resizes. There was a total of six sizes of the images that were inputted in the CNN for dataset 1(Cifar-10): 10x10,16x16,24x24,32x32,48x48and64x64. Thetrainingtimeforeach model was also another factor to examine. Each model was run for 50 epochs. 32 x 32 is the default image of this dataset and each pixel was divided by 255 to get values between 0 and 1.


## Experiment 2
For dataset 2 (Natural Images), this was also used to compare the training and testing accuracies of varying image resizes. However, since this dataset is more complex due to images being various sizes, the size ranges were examined with a box plot.The box plots show that the mean and min values would be interesting sizes to explore. While the max value in the 500-600 ranges were too large for the computer to resize, instead the 3rd quartile values were chosen as the max value. The values also show that the height and width’s mean, max and min values are not the same. So in order to to resize the image as a square, both values were averaged before inputting into the CNN architecture. Min Resize = 46 x 46, Mean Resize = 217 x 217, Max Resize = 550 x 550. For each of the three models, each pixel was divided by 255 to get values between 0 and 1. Then each of the models were run for 10 epochs. Due to the large sizes, the run time would be quite long if the epoch value was any larger. The labels would be one hot encoded to represent numerical values instead of string text. Cat to 0, Car to 1, Fruit to 2, Dog to 3, Person to 4, Flower to 5, Motorbike to 6 and Airplane to 7. The training set is split into 5520 images and the testing set contains 1379 images.

## Results




## Discussion
From the result tables, there is evidence that when resizing an image either smaller or larger, it affects the accuracy of the final testing run especially when examining Table 1. When training the models, the numbers show that the larger the image, the better the training accuracy and loss compared to the smaller images. But when testing, the models in Table 1 that are further away from the 32 x 32 default image, it tends to overfit and have a decreased accuracy and greater loss. In Table 2, the larger model testing accuracy is lower than the training accuracy which also shows signs of overfitting. As for runtime, the smaller the image, the faster the runtime. Even when running the 64 x 64 model in Table 1 or 550 x 550 model in Table 2, it takes over 75 minutes and 28 minutes respectively to complete training.

Even though dataset 2 images does not have a default size, the average size can be considered a good value that represents a default value similar in dataset 1. The best accuracies are using the default value or a size smaller but close to the default value. Larger resizes tend to have a longer runtime and a lower accuracy compared to a smaller resize.






