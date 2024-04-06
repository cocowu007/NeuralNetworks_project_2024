This repository contains all the materials for this Neural Networks course project, the purpose of the project is to train segmentation model on all public datasets.

# Project Information
Train an image segmentation model on all available public data. The key feature is that different datasets use different labeling schemes, and you do not want to convert all labels into common scheme (e.g., car, bicycle, pedestrian), because that would lose a lot of supervision signal (e.g., bus, truck, van would be all labeled as car). Instead, you should create a separate output head for each dataset with classes of that dataset. When doing backpropagation, you must mask out all the other output heads without the ground truth in the sum of losses, just keep the one loss for this dataset (labeling scheme). Now this can create very unbalanced gradients, if your batch does not contain images from all (or at least most) datasets. So, you need sample batches such that they contain at least one image from each dataset (or most datasets). This may be more than can fit in your GPU memory, so you might need to use gradient accumulation.

# Motivation
By creating separate output heads for each dataset, we aim to preserve the unique labeling characteristics of individual datasets without sacrificing valuable supervision signals. This approach allows us to leverage the rich information contained in different datasets while ensuring accurate segmentation results tailored to each dataset's specific classes.

# Data Collection
https://www.cityscapes-dataset.com/dataset-overview/
https://groups.csail.mit.edu/vision/datasets/ADE20K/
https://www.mapillary.com/dataset/vistas

# Team Members
Yucui Wu + ...




