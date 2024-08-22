# Furniture Image Classifier

This repo contains a Convolutional Neural Network model built to classify images of furniture into currently only 5 categories: Cabinets, Chairs, Fridges, Tables, and TVs. This model was designed as a stepping stone of learning for a future project idea in which an interior designer or anyone that owns a place can use an application that can interpret 2D photos of their room and images of furniture they want from online, turn them 3D and be used to virtually design their room.

The dataset I used to train the model: https://www.kaggle.com/datasets/udaysankarmukherjee/furniture-image-dataset
- In total, there are 15000 images, 3000 per category
- The distribution is split up as follows:
    - Train: 10,500 images, 2100 images per cat.
    - Valid: 2,000 images, 400 images per cat.
    - Test: 2,500 images, 500 images per cat.

## Model Architecture
The model is uses a pretrained base with ResNet50V2 to allow for faster convergence and for requiring less training data. The head then uses a couple of layers to finish out the classification. The Dropout layers help in preventing overfitting, which is needed when fine-tuning on a relatively small dataset and the combination of 2 Dense layers with an ReLU and Softmax activation functions allows the model to make accurate predictions across the 5 classes.

## Training Parameters
- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Batch Size: 64
- Epochs: 50