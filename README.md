# Tuberculosis-X-ray-Classification
![Banner Image](https://github.com/dmrossm/Tuberculosis-X-ray-Classification/blob/main/Images/Opening%20Slide.jpg)

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

### Multi-Layer Perceptron
My baseline model is a multilayer
perceptron (MLP)...to be continued.




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
├── Final_Notebook.ipynb                        <- documentation of project in Jupyter notebook with notation
├── Tuberculosis_Classification.pdf             <- PDF of project presentation
├── environment.yml                             <- file to be used to recreate environmental setup used while creating this project
└── presentation.pdf                            <- PDF version of project presentation
``` 

