# Satellite-images-semantic-segmentation

## About
An attempt at using semantic segmentation on satellite images to extract roads from satellite images.

## Data
For demonstration i have trained the model on  Massachusetts Roads Dataset (https://www.cs.toronto.edu/~vmnih/data/) however i developed a custom dataset from satellite images of New Delhi.

## Model
I have trained a UNET model modified such that inital images dimensions (H x W) are preserved in convolution [GitHub](https://github.com/aryaman4152/model-implementations-pytorch/tree/main/UNET).

The model was trained on image dimension of 1500x1500 (from train images) which took approcimately 70 minutes to train on a Tesla T4 GPU. Minimal transforms were applied on the data (see model_and_training.ipynb)

## Result 
(see Prediction.ipynb)
I ran the model on the image ![image](/images/image.png)
With has the expected mask ![image](/images/actual.png)
The output ![image](/images/output.png)

I believe the output can be imporoved with using better hyperparameters and more transforms. However in the actual mask it does not include roads leading up to houses whose trace can be seen in the predicted model.