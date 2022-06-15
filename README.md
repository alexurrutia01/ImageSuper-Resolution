# Simple Image Super-Resolution using a CNN

### Final Project Deep Learning UPF

<b>Problem:</b> reconstruct a high-resolution image from a single low-resolution image. In our case from 16x16 to 96x96.

<b>Goal:</b> Upscale and improve the quality of low resolution images.

The model has a total of 4 layers and each layer is a block consisting of a convolution, batch normalization, ReLU activation and upsampling.
![download](https://user-images.githubusercontent.com/72570569/173836534-2a66ec1e-3db9-4513-85b8-13cf1868b103.jpg)

The dataset used to train and test the images is the STL-10 dataset. (https://cs.stanford.edu/~acoates/stl10/)
- 100.000 unlabeled images
- Images are 96x96 pixels, in color.

The hyper-parameters used in training are:
- Batch size: 64
- Epochs: 10
- Learning rate: 0.0001
Also I use the Adam optimizer and Mean Squared Error loss.

#### Model 1: Training results (input images of 16x16)
![image](https://user-images.githubusercontent.com/72570569/173837371-d5c76207-dc6b-4188-a9d3-6333c36a47ee.png)
![image](https://user-images.githubusercontent.com/72570569/173837732-45eb6d72-205a-482f-b3e5-da79fc1531cd.png)

#### Model 2: Training results (input images of 32x32)
![image](https://user-images.githubusercontent.com/72570569/173838323-a98cdd13-eaac-4d0e-9f45-2bb8720269ea.png)

#### Conclusions
As we can see from the first model images of 16x16 pixels as input is too low of a resolution to recover but it is still a better than the input image.
In the second model for images of 32x32 pixels the input images are better but the reconstructed images are worse than the ones given as input to the model this is because minimizing the mean squared error gives higher noise to the image. Therefore, the reconstructed image fails to match the high resolution we expect.
 
#### Things to improve
To improve the performance of this model we can try to implement a ResNet (or a different model) or a ESRGAN (Enhanced Super Resolution GAN) instead of just doing upsamplings on the input image.
Another way to improve the model is to use more data (data augmentation) for training or use a dataset with images of higher resolution as the input, for example DIV2K.
