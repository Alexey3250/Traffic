# Traffic Sign Recognition
<img src="https://i.imgur.com/0w8qDPz.jpg">


## Overview
This project aims to develop a neural network model to classify traffic signs using the German Traffic Sign Recognition Benchmark (GTSRB) dataset. The model is built and trained using TensorFlow and achieves high accuracy in distinguishing among 43 different traffic sign categories.

<img src="https://i.imgur.com/xeDJYDH.png">

## Project Structure
- `traffic.py`: Main Python script that loads data, defines the neural network model, trains the model, and evaluates its performance.
- `gtsrb`: Directory containing the dataset with subdirectories for each category of traffic signs.
- `requirements.txt`: Contains a list of dependencies to install using pip.

## Installation
Before running the project, install the required dependencies:

```bash
pip3 install -r requirements.txt
```

## Dataset
The dataset used is the GTSRB dataset, which includes thousands of labeled images of 43 different kinds of road signs.

## Usage
To train the neural network model, run:

```bash
python traffic.py gtsrb [model.h5]
```

Where `gtsrb` is the directory containing the dataset and `model.h5` is the optional filename to save the trained model.

## Neural Network Model
The `get_model` function in `traffic.py` returns a compiled convolutional neural network model with the following layers:
- Convolutional layers with varying numbers of filters
- Max pooling layers
- Batch normalization layers
- Dense layers with dropout for regularization

## Performance
The model's performance after training for 10 epochs is as follows:
- Training Accuracy: **99.24%**
- Validation Accuracy: **98.74%**
- Training Loss: **0.0258**
- Validation Loss: **0.0425**
<img src="https://i.imgur.com/aLwdRDN.png">

## Files
- `model.h5`: Saved model after training (if provided as a command-line argument).
