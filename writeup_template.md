# **Traffic Sign Recognition** 

## Writeup

### You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---

**Build a Traffic Sign Recognition Project**

The goals / steps of this project are the following:
* Load the data set (see below for links to the project data set)
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Analyze the softmax probabilities of the new images
* Summarize the results with a written report


[//]: # (Image References)

[image1]: ./examples/visualization.jpg "Visualization"
[image2]: ./examples/grayscale.jpg "Grayscaling"
[image3]: ./examples/random_noise.jpg "Random Noise"
[image4]: ./examples/placeholder.png "Traffic Sign 1"
[image5]: ./examples/placeholder.png "Traffic Sign 2"
[image6]: ./examples/placeholder.png "Traffic Sign 3"
[image7]: ./examples/placeholder.png "Traffic Sign 4"
[image8]: ./examples/placeholder.png "Traffic Sign 5"

## Rubric Points
### Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/481/view) individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one. You can submit your writeup as markdown or pdf. You can use this template as a guide for writing the report. The submission includes the project code.

You're reading it! and here is a link to my [project code](https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project/blob/master/Traffic_Sign_Classifier.ipynb)

### Data Set Summary & Exploration

#### 1. Provide a basic summary of the data set. In the code, the analysis should be done using python, numpy and/or pandas methods rather than hardcoding results manually.

Basic things like the number of examples ,the number of classes have been displayed.<br>
Apart from this random images are also displayed.<br>

#### 2. Include an exploratory visualization of the dataset.

A graph is plotted using python SEABORN displaying the counts of every class along with the class name.<br>
To accomodated the large number of classes it is plotted horizontally<br>
It is made more visually pleasing by using seaborn instead of matplotlib<br>


### Design and Test a Model Architecture

#### 1. Describe how you preprocessed the image data. What techniques were chosen and why did you choose these techniques? Consider including images showing the output of each preprocessing technique. Pre-processing refers to techniques such as converting to grayscale, normalization, etc. (OPTIONAL: As described in the "Stand Out Suggestions" part of the rubric, if you generated additional data for training, describe why you decided to generate additional data, how you generated the data, and provide example images of the additional data. Then describe the characteristics of the augmented training set like number of images in the set, number of images for each class, etc.)

I did image normalization and converting images to grayscale.<br>
There was no need for image augmentation as i recieved 96% accuracy wihout it<br>

#### 2. Describe what your final model architecture looks like including model type, layers, layer sizes, connectivity, etc.) Consider including a diagram and/or table describing the final model.

My final model consisted of the following layers:

---------<br>
Variables: name (type shape) [size]<br>
---------<br>
w1:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable:0 (float32_ref 20) [20, bytes: 80]<br>
w2:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_1:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_2:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_3:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_4:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_5:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_6:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_7:0 (float32_ref 43) [43, bytes: 172]<br>
w1_1:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_8:0 (float32_ref 20) [20, bytes: 80]<br>
w2_1:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_9:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_10:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_11:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_12:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_13:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_14:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_15:0 (float32_ref 43) [43, bytes: 172]<br>
w1_2:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_16:0 (float32_ref 20) [20, bytes: 80]<br>
w2_2:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_17:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_18:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_19:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_20:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_21:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_22:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_23:0 (float32_ref 43) [43, bytes: 172]<br>
w1_3:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_24:0 (float32_ref 20) [20, bytes: 80]<br>
w2_3:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_25:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_26:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_27:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_28:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_29:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_30:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_31:0 (float32_ref 43) [43, bytes: 172]<br>
w1_4:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_32:0 (float32_ref 20) [20, bytes: 80]<br>
w2_4:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_33:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_34:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_35:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_36:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_37:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_38:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_39:0 (float32_ref 43) [43, bytes: 172]<br>
w1_5:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_40:0 (float32_ref 20) [20, bytes: 80]<br>
w2_5:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_41:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_42:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_43:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_44:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_45:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_46:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_47:0 (float32_ref 43) [43, bytes: 172]<br>
w1_6:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_48:0 (float32_ref 20) [20, bytes: 80]<br>
w2_6:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_49:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_50:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_51:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_52:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_53:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_54:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_55:0 (float32_ref 43) [43, bytes: 172]<br>
w1_7:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_56:0 (float32_ref 20) [20, bytes: 80]<br>
w2_7:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_57:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_58:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_59:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_60:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_61:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_62:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_63:0 (float32_ref 43) [43, bytes: 172]<br>
w1_8:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_64:0 (float32_ref 20) [20, bytes: 80]<br>
w2_8:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_65:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_66:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_67:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_68:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_69:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_70:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_71:0 (float32_ref 43) [43, bytes: 172]<br>
w1_9:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_72:0 (float32_ref 20) [20, bytes: 80]<br>
w2_9:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_73:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_74:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_75:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_76:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_77:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_78:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_79:0 (float32_ref 43) [43, bytes: 172]<br>
w1_10:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_80:0 (float32_ref 20) [20, bytes: 80]<br>
w2_10:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_81:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_82:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_83:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_84:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_85:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_86:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_87:0 (float32_ref 43) [43, bytes: 172]<br>
w1_11:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_88:0 (float32_ref 20) [20, bytes: 80]<br>
w2_11:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_89:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_90:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_91:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_92:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_93:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_94:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_95:0 (float32_ref 43) [43, bytes: 172]<br>
w1_12:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_96:0 (float32_ref 20) [20, bytes: 80]<br>
w2_12:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_97:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_98:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_99:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_100:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_101:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_102:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_103:0 (float32_ref 43) [43, bytes: 172]<br>
w1_13:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_104:0 (float32_ref 20) [20, bytes: 80]<br>
w2_13:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_105:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_106:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_107:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_108:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_109:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_110:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_111:0 (float32_ref 43) [43, bytes: 172]<br>
w1_14:0 (float32_ref 5x5x1x20) [500, bytes: 2000]<br>
Variable_112:0 (float32_ref 20) [20, bytes: 80]<br>
w2_14:0 (float32_ref 5x5x20x40) [20000, bytes: 80000]<br>
Variable_113:0 (float32_ref 40) [40, bytes: 160]<br>
Variable_114:0 (float32_ref 1000x250) [250000, bytes: 1000000]<br>
Variable_115:0 (float32_ref 250) [250, bytes: 1000]<br>
Variable_116:0 (float32_ref 250x84) [21000, bytes: 84000]<br>
Variable_117:0 (float32_ref 84) [84, bytes: 336]<br>
Variable_118:0 (float32_ref 84x43) [3612, bytes: 14448]<br>
Variable_119:0 (float32_ref 43) [43, bytes: 172]<br>
Total size of variables: 4433235<br>
Total bytes of variables: 17732940<br>
 


#### 3. Describe how you trained your model. The discussion can include the type of optimizer, the batch size, number of epochs and any hyperparameters such as learning rate.

To train the model, I used an Adam optimizer with a batch size of 64.<br>
the number of epochs is 20 which was increased accordingly to reach necessary accuracy<br>

#### 4. Describe the approach taken for finding a solution and getting the validation set accuracy to be at least 0.93. Include in the discussion the results on the training, validation and test sets and where in the code these were calculated. Your approach may have been an iterative process, in which case, outline the steps you took to get to the final solution and why you chose those steps. Perhaps your solution involved an already well known implementation or architecture. In this case, discuss why you think the architecture is suitable for the current problem.

My final model results were:<br>
Train Accuracy = 0.976<br>
Validation Accuracy = 0.818<br>
Test Accuracy = 0.807<br>

If an iterative approach was chosen:<br>
I was facing very low accuracy of 53 % .<br>
Also it was constant but not increasing<br>
This can be checked in Traffic signal classifier - Copy <br>
I made changes in the architecture by increasing the number of filters but to no avail.<br>
I finally got the break through on shuffling the data set 

## EXTRA RESOURCES ATTACHED
1) In model files the model dat is saved.<br>
2) In internet images , images downloaded from the internet for testing have been saved <br>
3) In graphs data for visulization for tensorboard have been saved<br>
4) In tensorboard screenshots of loss,accuracy and the model graphs as well as the csv have been saved<br>
5) In layer 1 visualizations of weights have been saved<br>
6) In layer 2 visualizations of weights have been saved <br>

### Test a Model on New Images

#### 1. Choose five German traffic signs found on the web and provide them in the report. For each image, discuss what quality or qualities might be difficult to classify.

The images are displayed in the python notebook.<br>

#### 2. Discuss the model's predictions on these new traffic signs and compare the results to predicting on the test set. At a minimum, discuss what the predictions were, the accuracy on these new predictions, and compare the accuracy to the accuracy on the test set (OPTIONAL: Discuss the results in more detail as described in the "Stand Out Suggestions" part of the rubric).


The model is not predicting the signs accurately.<br> 
This could be because the images taken from the net are more clear as compared to images in the trainting set.<br>
One puzzling thing is that the redictions keep changing with every run.<br>
Sometimes there are 2-3 out of 5 images correct and while running agin the predictions change where non are matching.<br>

#### 3. Describe how certain the model is when predicting on each of the five new images by looking at the softmax probabilities for each prediction. Provide the top 5 softmax probabilities for each image along with the sign type of each probability. (OPTIONAL: as described in the "Stand Out Suggestions" part of the rubric, visualizations can also be provided such as bar charts)



### (Optional) Visualizing the Neural Network (See Step 4 of the Ipython notebook for more details)
#### 1. Discuss the visual output of your trained network's feature maps. What characteristics did the neural network use to make classifications?


I could not get to display the activations but I tried visualizing the wieghts which are saved in layer1 & layer 2 folders