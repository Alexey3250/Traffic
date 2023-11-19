# Traffic Sign Recognition with 98.74% Accuracy
<img src="https://i.imgur.com/0w8qDPz.jpg">

# Youtube Video

[![Watch the video](https://img.youtube.com/vi/cGvT-y1VWfY/hqdefault.jpg)](https://youtu.be/cGvT-y1VWfY?si=iePNO_3GFu_5ca81)

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


## Experimentation Process

### Model Structure

During the development of the traffic sign recognition model, a variety of neural network architectures were tested to determine the most effective structure. The goal was to maximize accuracy while minimizing overfitting.

The final structure that yielded the best results was a convolutional neural network (CNN) composed of several layers. The model begins with two convolutional layers with 16 and 32 filters, respectively, each followed by a max pooling layer to reduce dimensionality. This is complemented by batch normalization to accelerate training. The network then extends into deeper convolutional layers with increased filters (64 and 128), which are designed to capture more complex patterns in the data.

A key observation during testing was that adding more convolutional layers beyond this point resulted in diminishing returns. The additional complexity did not significantly improve performance on the test set, which suggested that the model had reached an optimal level of complexity for the task at hand.

### Optimizers

Various optimizers were trialed including SGD, RMSprop, and Adam. Adam optimizer emerged as the clear leader, providing the best balance between speed and accuracy. It was noted that while SGD initially made rapid improvements, it plateaued quickly and failed to converge to an optimal solution within the epoch limit. RMSprop, while faster than SGD, did not achieve the same accuracy levels as Adam.

The Adam optimizer's adaptive learning rate proved to be particularly beneficial for this dataset, as it helped in efficiently navigating the high-dimensional weight space of the neural network. The use of Adam also reduced the need for fine-tuning the learning rate and momentum parameters, simplifying the training process.

### Conclusion

The combination of a carefully designed CNN architecture and the Adam optimizer led to a model that performs with high accuracy on both the training and validation sets. This model structure and optimizer choice proved to be robust across various tests, indicating a good generalization capability on unseen traffic sign images.