# Machine Learning Binary Classification for Images

When searching for "outdoors" in Google Photos, the application quickly displays images of parks, blue skies, and beaches. Similarly, searching for "indoors" yields images featuring ceilings, household objects, windows, and doors. I am interested in replicating this type of classification for my own photos using various machine-learning binary classification models (KNN, logistic regression, and CNN) and comparing their accuracy and efficiency.

I am working with a dataset of 100 photos: 50 labeled as "indoors" and 50 as "outdoors." These photos were taken over the past ten months in London, Scotland, Houston, Faro, Berlin, and San Francisco.

For the "indoors" label, I classified images taken under a roof, such as those inside planes or on terraces, or those with sufficient context to be recognized as indoor. The "outdoors" label included photos taken in open environments, like streets, building facades, and other exterior settings. To create a more diverse dataset, I also included images that lack clear cues but provide enough contextual information to update the model and improve its generalizability. The model will need to determine whether each image was captured indoors or outdoors, relying on macro cues like lighting, object types, shapes, colors, and shading.

To avoid overfitting and ensure the model's predictions aren't random, I will perform a 70-30 train-test split. Seventy percent of the data (70 photos) will be used for training, while the remaining 30% (30 photos) will be reserved for testing the model's performance.

![image](https://github.com/user-attachments/assets/b1d64476-a9c6-410d-944f-55bcdb76b222)

## RGB distribution over the dataset
Below we see the distribution of the color channels (RGB) for different classes of images. I hypothesize the model will use the standard deviation and the mean difference for the blue channel for indoor and outdoor images, respectively, to learn and sort out the classes of images. The statistics can be found in the ([outdoor-indoor-classifier/binary_classification_1.ipynb](https://github.com/steniodeassis/outdoor-indoor-classifier/edit/main/README.md)).

![image](https://github.com/user-attachments/assets/60d174d4-4679-491e-a0e9-a0cd8989115d)


## Improved Version

binary-classification-2 is an improved version of binary-classification-1, where I used data augmentation to increase the training and testing data from 100 images to 1100. Besides, the second project also includes a dimensionality reduction analysis using PCR, autoencoders and clustering.

![image](https://github.com/user-attachments/assets/d7feee81-8fa2-471c-be9a-c699a01f8df8)

## RGB distribution over the dataset
Similarly, we see the RGB distribution after the augmentation. The differences in standard deviation and mean for the blue channels for outdoor and indoor images are slightly more apparent.

![image](https://github.com/user-attachments/assets/c2c2a719-725c-44e3-acd0-93afd851ae4f)


In the following, I show the different accuracies for Logistic Regression (LR), K-near-neighbors (KNN), and Convolution Neural Network (CNN).

| ML Model   | 1st Project | 2nd Project |
|----------|----------|----------|
| LR   | 0.67 | 0.84  |
| KNN  | 0.77 | 0.86 |
| CNN  | 0.71 | 0.94 |

So, by increasing the training data, we managed to improve the performance of the model; however, we still have to ensure this is not due to overfitting.
