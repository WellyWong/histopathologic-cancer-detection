## histopathologic-cancer-detection
https://nbviewer.org/github/WellyWong/histopathologic-cancer-detection/blob/main/histopathologic_cancer_detection_classifier.ipynb

### Overview
This is a Kaggle mini-project for DTSA 551 - Introduction to Deep Learning. An algorithm was developed to detect metastatic cancer from small patches taken from larger digital pathology scans. The histopathological image dataset comes from Kaggle, it is a slightly modified version of the PatchCamelyon (PCam) benchmark dataset. The original PCam contains duplicate images due to its probabilistic sampling. The version presented on Kaggle does not contain duplicates.

Examining histopathologic slides manually is a tedious and time-consuming task, as a large area of tissue has to be examined and small metastases can be easily missed, thus making it an ideal prospect for automation using machine learning techniques.

The dataset is relatively small. Therefore, to avoid overfitting, we apply image augmentation during training using the ImageDataGenerator from Keras.

![image_augmentation](https://github.com/WellyWong/histopathologic-cancer-detection/assets/70742141/41f02e3b-b707-472e-afb3-eed4be57ae7d)

Augmentations of the same original image by the ImageDataGenerator in Keras

### Model Architecture
To establish a baseline, we began with a relatively simple model. Convolutional Neural Network was used for feature extraction, and classification was done using Fully Connected Artificial Neural Network. Initially, we train edclassic networks such as LeNet5, and subsequently, we constructed our custom CNN model. We utilized transfer learning and fine-tune a pre-trained model (DenseNet169) to our dataset.

### Model Evaluation
![models_roc](https://github.com/WellyWong/histopathologic-cancer-detection/assets/70742141/13ce2b93-b8d6-4d7d-b887-66aede00dd5a)

Receiver Operating Chracteristic (ROC) curve of the three chosen models

### Kaggle Submission Result
Weighted predictions from DenseNet169 base model and Custom CNN model resulted in improved predictions on Kaggle test data.

![kaggle_score_assembled_model](https://github.com/WellyWong/histopathologic-cancer-detection/assets/70742141/9de7c603-249a-4266-ad78-85a1ce265c69)

Screenshot of Kaggle Leaderboard
