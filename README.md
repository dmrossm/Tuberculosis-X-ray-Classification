# Tuberculosis-X-ray-Classification

## Background
Tuberculosis (TB) is an infectious disease caused by the effect of Mycobacterium tuberculosis
on the body, most specifically, the lungs. Roughly 25% of our global population is infected with
Mycobacterium tuberculosis, most of whom have what is known as “latent tuberculosis.” This
means that they have subclinical cases and show no signs of disease and cannot spread the
infection to others. 10% of these individuals will go on to develop active TB (2.5% of the global
population). “Eight countries accounted for two thirds of the new TB cases: India, China,
Indonesia, the Philippines, Pakistan, Nigeria, Bangladesh and South Africa.”
While the cost for initial testing can and has been reduced, the cost of follow-up imaging and
interpretation remains expensive. 

## Business Need
Given the poverty experienced in the countries experiencing
the highest TB case counts, The World Health Organization wishes to offer cheaper assessment
of X-ray images obtained from patients so as to greatly aid in the reduction of active cases by
allowing doctors to assess lung images more often. Given this need, a neural network that can
classify X-ray images as having come from patients with TB, verus from patients without TB or
with latent TB, would be extremely useful in active case reduction.

## Data Understanding
- Researchers and doctors from Qatar University, the University of Dhakaalong and Hamad
Medical Corporation amassed a database of chest X-rays (CXRs) of TB-positive and TB-negative cases,
consisting of ~7000 images. The data is balanced and consists of 50% TB-positive and 50%
TB-negative cases/X-rays.([Link to academic paper](https://ieeexplore.ieee.org/document/9224622)) The database can be accessed via [Kaggle](https://www.kaggle.com/tawsifurrahman/tuberculosis-tb-chest-xray-dataset).
- Roughly 7,000 additional CXRs from patients with TB are available via the National Institutes of health. These are 

## Data Preparation
I will prepare the data by first exploring (and visualizing) the distribution of image sizes. If the
images are not of a standard size, I will standardize the size of all images. Next I will scale the
red/green/blue contributions by dividing by 255 to scale each contribution to a range between -1
and 1. Once I have completed EDA and data preparation, I will perform two test train splits in
order to set aside a training set, a testing set and final validation set.
