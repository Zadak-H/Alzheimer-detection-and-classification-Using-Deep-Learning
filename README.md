# Alzheimer-detection-and-classification-Using-Deep-Learning

## **Problem Definition**

>*Alzheimer is known the most for the causes of dementia. It takes 2/3 of the whole dementia popilation, while the cause is still unknown. According to papers from Lancet neurology, even the old theory such as neural inflations, which was disregarded as the cause compared to tau-protein, beta-amiloids, and genetic factors (Apo E4).*


Before I start, I'll have to explain a bit more about the Alzheimer, because, the data contains 4 classes of Alzheimer that depends on the severity of dementia.

There are degrees of severity in Alzheimer.

*   Very mildly demented : This is the stage where patient starts to forget where they put their stuff, other people's names recently, etc. It is hard to detect through cognitive ability test.

*   Mildly demented : This is the stage where patients don't remember the words, can't find their way to the destination, loss of focus and work-abilities. This is also the stage where patients even forget that they are losing memory. From this stage, with cognitive testing, it can be found.

*   Moderately demented : Starts to forget the recent activities, important old histories, have hard time calculating the budget, hard to go outside alone, and loss of empathy.

There are 3 more stages in the moderately dementia, which in the terminal stage, the patient can't move on their own, while they lose the ability to speak. But I assume that the current dataset from Kaggle [https://www.kaggle.com/datasets/sachinkumar413/alzheimer-mri-dataset] is considering all the these stages merged inside 'Moderately demeted' or not even considered.

Knowing these stages are important because the faster the stage the patient is at, the treatment will have higher effect in terms of slowing the process. If the dementia is found during the moderately demented stage, it is known that the patient will pass away in 3 years. (One of the reported case is a rythm guitarists Malcom from the band AC/DC was diagnosed severe dementia at 2014.)

Thus, having an AI that detects alzheimer dementia in the early stage can allow longer life expactancy from the patient as well as higher life quality overall from the slowdown of dementia.

As Alzheimer can not only be found with cognitive ability testing, but also through MRI or CT by looking at the ventricles of the brain and cortical atrophy, the theoratical foundation on this project is solid. Doctors find the patient with Alzheimer's have a brain that have enlarged ventricles (that lies in the center of the brain) as well as thinner cortical grey area of the brain.

## **Solution Specification**

> *This project will go through various Deep Learning models from Convolutional Neural Network models using reLU for Detection and Classification.
In this Project I will use GANs for Superresolution the images and then I will use GANs for Synthetic Image generation For getting more test and train images.*

## About Dataset

### Alzheimer MRI Preprocessed Dataset (128 x 128)

>*The Data is collected from several websites/hospitals/public repositories. <br>
The Dataset is consists of Preprocessed MRI (Magnetic Resonance Imaging) Images. <br>
All the images are resized into 128 x 128 pixels. <br>
The Dataset has four classes of images. <br>
The Dataset is consists of total 6400 MRI images. <br>
Class - 1: Mild Demented (896 images) <br>
Class - 2: Moderate Demented (64 images) <br>
Class - 3: Non Demented (3200 images) <br>
Class - 4: Very Mild Demented (2240 images)*


### The Random image collected from 4 Classes ->
![Input Data](Output/Image.png)

## EDA and Preprocessing
Firstly, GANs will be applied to generate some more images as a datatset, then if it is implemeted successfully then we will try SRGANs for getting better resolution and will use this as a data preprocessed.

### What is DCGANS ?
Generative Adversarial Networks (GANs) are one of the most interesting ideas in computer science today. Two models are trained simultaneously by an adversarial process. A generator ("the artist") learns to create images that look real, while a discriminator ("the art critic") learns to tell real images apart from fakes. During training, the generator progressively becomes better at creating images that look real, while the discriminator becomes better at telling them apart. The process reaches equilibrium when the discriminator can no longer distinguish real images from fakes.

## Our GANs Model
![GAN MODEL](Output/GanModel.png)

### Real Input Exaple and Noisy Fake Input Data
![Real](Output/batchinput.png) ![Fake](Output/fakeimage.png)

### Synthetic Input Dataset Creation using DCGANs
![Real](Output/syntheticimage.png)

### DCGANs Loss and Score
![Loss](Output/ganLoss.png) ![Score](Output/ganScore.png)

### New Generated Alzheimer MRI Preprocessed Dataset

>*The Dataset is consists of Preprocessed MRI (Magnetic Resonance Imaging) Images. <br>
The Dataset has four classes of images. <br>
The Dataset is consists of total 6856 MRI images. <br>
Class - 1: Mild Demented (1352 images) <br>
Class - 2: Moderate Demented (64 images) <br>
Class - 3: Non Demented (3200 images) <br>
Class - 4: Very Mild Demented (2240 images)*

![Data](Output/data.png)

## Classification And Prediction
In our model we have used the CNN2D for classification and prediction purpose and it gives an excelent accurecy with very minimum loss.

### CNN Model
![CNN model](Output/CnnModel.png)

### Train, Test & Validation
In our project we used **80% for Train** , **10% for Test**, and **10% for Validation**

## Training, Accuracy and Validation Plot
### Training data accuracy and loss
![ACC_Loss](Output/trainingdataAcc_loss.png)
### Training and Validation Accuracy
![Acc](Output/Acc.png)
### Training and Validation Loss
![train_val_loss](Output/train_val_loss.png)

## Prediction 
![Prediction](Output/Prediction.png)

## Conclusions

By (1) using DCGANs generate Synthetic Image data; (2) Using SRGANs to super resolutions the synthetic images; and (3) manually setting the CNN model, I was able to achieve **0.99 recall** and **0.99 accuracy** from my best model, Rescaling -> Conv2D -> MaxPooling 2D -> Conv2D -> MaxPooling 2D -> Dropout -> Conv2D -> MaxPooling 2D -> Dropout -> Flatten -> Dense -> Dense -> Dense ,  which is more better than other nodels.

## Libraries

Standard packages for data analysis and visualization are required–[NumPy](https://numpy.org/), [Pandas](https://pandas.pydata.org/), [Matplotlib](https://matplotlib.org/), and [Seaborn](https://seaborn.pydata.org/), [scikit-learn](https://scikit-learn.org/stable/index.html), [Tensorflow](https://www.tensorflow.org/), [Keras](https://keras.io/), for a number of classifiers.


## Contributing

Due to the nature of the project, this project is not open to contributions. If, however, after looking at the project you'd like to give advice to someone new to the field and eager to learn, please reach out to me at [rajarshi921@gmail.com]

## Author

**Rajarshi SinhaRoy** <br/>



## Acknowledgments
Thanks to [Kaggle](https://www.kaggle.com) for access to data found in [Alzheimer MRI Preprocessed Dataset](https://www.kaggle.com/datasets/sachinkumar413/alzheimer-mri-dataset)
