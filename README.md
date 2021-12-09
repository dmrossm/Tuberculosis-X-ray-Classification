# Tuberculosis-X-ray-Classification
![Banner Image](https://github.com/dmrossm/Tuberculosis-X-ray-Classification/blob/main/Images/Opening%20Slide.jpg)

- Please note that the final notebook is within the main repository, not within the notebooks folder.

## Background
Tuberculosis (TB) is an infectious disease caused by the effect of Mycobacterium tuberculosis
on the body, most specifically, the lungs. [Roughly 25% of our global population is infected with
Mycobacterium tuberculosis, most of whom have what is known as “latent tuberculosis.”](https://www.who.int/news-room/fact-sheets/detail/tuberculosis) This
means that they have subclinical cases and show no signs of disease and cannot spread the
infection to others. 10% of these individuals will go on to develop active TB (2.5% of the global
population). [“Eight countries accounted for two thirds of the new TB cases: India, China,
Indonesia, the Philippines, Pakistan, Nigeria, Bangladesh and South Africa.”](https://www.who.int/news-room/fact-sheets/detail/tuberculosis)
While the cost for initial testing can and has been reduced, the cost of follow-up imaging and
interpretation remains expensive. 

## Business Need
Given the poverty experienced in the countries experiencing
the highest TB case counts, [The World Health Organization](https://www.who.int/) wishes to offer cheaper assessment
of X-ray images obtained from patients so as to greatly aid in the reduction of active cases by
allowing doctors to assess lung images more often. Given this need, a neural network that can
classify X-ray images as having come from patients with TB, verus from patients without TB or
with latent TB, would be extremely useful in active case reduction.

## Data Understanding
- Researchers and doctors from Qatar University, the University of Dhakaalong and Hamad
Medical Corporation amassed a database of chest X-rays (CXRs) of TB-positive and TB-negative cases,
consisting of 4200 images. The data is imbalanced and consists of ~17% TB-positive and ~83%
TB-negative cases/X-rays.([Link to academic paper](https://ieeexplore.ieee.org/document/9224622)) The imaging data can be accessed via [Kaggle](https://www.kaggle.com/tawsifurrahman/tuberculosis-tb-chest-xray-dataset).
![Banner Image](https://github.com/dmrossm/Tuberculosis-X-ray-Classification/blob/main/Images/training_images.png)


## Data Preparation
I began by downloading all images and arranging them locally into training, validation and testing data, each representing 70%, 20% and 10% of the images respectively. I prepared the data by first exploring image sizes to assure standardized sizes. Next I scaled the
red/green/blue contributions by dividing by 255 to scale each contribution to a range between -1
and 1. Then I demonstratd the class imbalance with a bar plot. (I hope to eliminate this class imbalance once I wrangle the NIH data a bit more.

## Modeling
- I aimed to maximize accuracy and recall in order to minimize false negatives (i.e., patients with tuberculosis being classified as normal). 
- My baseline model is a simple multilayer perceptron (MLP) model with one hidden layer using the tanh activation function. I used the sigmoid function as the activation function for the output layers for all models, since this is a binary classification project. Validation recall was immediately at zero for this first model (i.e., the false negative rate was at a maximum) and the model remained at zero recall for all epochs. It is apparently always predicting that a chest x-ray is "normal." This is apparent because the validation accuracy is equivalent to the percentage of images that are normal (83%).
- My second model is another multi-layer perceptron. It has one hidden layer using the relu activation function instead of the tanh activation function. This model has done far better. It is no longer predicting only one class. The validation accuracy and validation recall achieved in epoch 6 were impressive and were 92% and 90%, respectively. I will returned to this model when more optimal metrics were not acheived with further modeling.
- My third model is yet another multi-layer perceptron with a one hidden layer (relu activation function used again) and dropout layer(25%). The model demonstrated the same issue as the first model. It is apparently always predicting that a chest x-ray is "normal." This is apparent because the validation accuracy is equivalent to the percentage of images that are normal (83%).
- My fourth model is once again a multi-layer perceptron, with two hidden layers (relu activation function) and two dropout layers(25%). While this model achieved impressive validation accuracy scores above 90% and avoided overfitting, its validation recall scores were subpar and remained below 76%.
- My fifth model was a convolutional neural network with 3 pairs of double convolution layers before pooling. While this model achieved validation accuracy of 95% and validation recall of 81%, there was more overfitting seen here then in my third model which achieved scores of 91% for both metrics. As surprising as this seems the third simple multilayer perceptron appears to be the best model to classify this dataset.

## Final Model 
- A simple multilayer perceptron with one hidden layer using the relu activation function and an output layer using the sigmooid activation function.
- Validation Accuracy: 92%
- Validation Recall: 90%
![Banner Image](https://github.com/dmrossm/Tuberculosis-X-ray-Classification/blob/main/Images/Confusion_Matrix.jpg)

## Conclusions
- While altering various hyperparameters and changing the shapes and depths of these neural networks, varying levels of the key metrics (accuracy and recall) were achieved. I used the sigmoid function as the activation function for the output layers of all models, since this is a binary classification project. My second model, a simple multilayer perceptron with one hidden layer using the relu activation function, showed promise with maximum validation accuracy and validation recall both at 92% and 90%, respectively (without significant overfitting). My first, third and fourth models all always predicting that a chest x-ray was "normal." This was apparent because the validation accuracy was equivalent to the percentage of images that were normal (83%) within the dataset. My fifth model was a convolutional neural network with three sets of double convulutional layers before pooling. While this model achieved validation accuracy of 95% and validation recall of 81%, there was more overfitting seen here then in my third model which acheived a higher validation recall score. As surprising as this seems the third simple multilayer perceptron appears to be the best model to classify this dataset.

## Next Steps
- Future steps include: testing this tool in a rural and urban area and calculating how many more cases it predicts accurately than the participating physicians, the decrease in care delay and the decrease in unecessary spread of tuberculosis in those testing regions.



## Repository Structure

```
├── Images                                      <- Folder containing Chest X-rays: test, train and validation sets
│   └── ...
├── Notebooks                                   <- practice notebooks with model iterations not included in final nnotebook                  
│      └── ...
├── TB_Chest_Radiography_Database
│       └── ...                        
├── .gitignore
├── README.md                                  
├── Tuberculosis-X-ray-Classification.ipynb     <- Narrative documentation of project in Jupyter notebook
├── environment.yml                             <- file to be used to recreate environmental setup used while creating this project
└── presentation.pdf                            <- PDF version of project presentation
``` 

