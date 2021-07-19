# MTARSI
Multi type aircraft Remote sensing Images - Classification
______________________

**Multi-type Aircraft Remote Sensing Images(MTARSI)** dataset contains **9385 images** of **20 aircraft types.** 

This dataset has,
- Varied backgrounds
- Different resolutions
- Distinct poses of aircrafts

### Finding the **resolution of the images** to **resize the dataset** accordingly

> Neural networks receive inputs of the same size, **all images** need to be **resized to a fixed size before inputting** them to the **CNN**.

> For this purpose, we selected a **resolution of 80 X 80 as an input for our model**, since there were images with varied resolutions, we picked the image with minimum resolution rather than padding the lower reoslution images.

## Preprocessing steps:
1. Resizing
2. Normalization

## Split dataset into train, validation and test
Train: 7508
<br> Validation: 1501
<br> test : 376

Train Test Split ratio - 80: 20

## Model Building:
1. The model consists of four blocks of convolution with 3X3 kernels with maxPooling layer connecting them 
2. Batch Normalization is used to normalize the image batches in each layer
3. ReLu activation is used to induce non-linearity to our model
4. We are using Padding to keep the image size consistent through the convolution block
5. In block 3, 128 features are extracted and flattened before passing it to the Fully Connected layer(FC layer/Dense layer) with 32 hidden units.
6. In Output layer, softmax activation is used to provide the probablities for 20 classes.
7. Dropout 0.2 provides a regularization effect by randomly dropping off 20% of the neurons in the FC layer.

## Model Training

1. **Loss funtion:** 'Categorical crossentropy' . Used in Multi-class classification tasks
2. **Optimizer:** 'Adam' derived from Adaptive moment estimation
3. **Metrics:** Accuracy, Precision, Recall
4. **LR scheduler** used reduces learning rate by a factor of 10 (lr/10) for every epoch after 10th epoch.
5. **Early stopping**: When the model performance isn't improving for two consecutive epochs, training is stopped and mode is saved.

## Hyperparamters used:
**learning rate** (lr = 0.0001)
<br>**batch size**  (batch size =16)
<br>**number of epochs** (epochs = 25)

### Misclassified Images

### Confusion Matrix

### GradCAM Implementation

### Class wise accuracy and Classification report

### Insights





