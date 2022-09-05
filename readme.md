## Tools / Libraries used
Seaborn
Numpy
Keras / Tensorflow
Matplotlib

## Dataset
- [Intel Image Classification](https://www.kaggle.com/puneet6060/intel-image-classification)
Extract this into local data/ (data/seg_pred, data/seg_test, data/seg_train)

### Problem Statement
Can we build an accurate convolutional neural network to accurately classify images into six categories - buildings, forest, glacier, mountain, sea, and street?

### The Data
The provided dataset included 14,000 images for training (in six folders, presorted by category), 3,000 images for testing (again, presorted by category), and 7,000 images for predicting (although the Kaggle competition to which those predictions could be submitted is no longer running).

For our purposes, only the training and test datasets were used.

### Methods

First, we used Keras to import the training and testing images via directory (maintaining the existing folder structure to maintain correct image categorization). Then we built and trained a custom convolutional neural network to predict which of those six categories unseen images belonged to. That custom model performed at 67% accuracy (vs a baseline of 16.6%).

Then, we implemented the EfficientNetV2L model - a pre-built and trained deep learning model for general image classification. We then customized that model with a few layers to allow it solve our particular classification problem, while leaving the main model unchanged. That model performed at 90% accuracy, and was selected as our final model.

Finally, we created a confusion matrix to look at which categories the model was most accurate at predicting. Unsurprisingly, it was hardest to differentiate between mountains vs glaciers and streets vs buildings, but even those categories the model was accurate more than 80% of the time.

### Conclusions and results

Convolutional neural networks (CNN) are extremely powerful tools for automated image categorization. However, to get the most out of a CNN requires complex architecture, extremely deep models with very large numbers of parameters, and huge datasets for effective training. However, the availability of pre-trained models within Keras make it much easier to customize a model for a smaller dataset, and we highly recommend that approach for anyone working on an image classification problem with a small dataset.
