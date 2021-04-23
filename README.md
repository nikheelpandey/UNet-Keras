# Ultrasound Nerve Segmentation using U-Net

This tutorial shows how to use [Keras library](http://keras.io/) to build deep neural network for ultrasound image nerve segmentation.
More info on this Kaggle competition can be found on [https://www.kaggle.com/c/ultrasound-nerve-segmentation](https://www.kaggle.com/c/ultrasound-nerve-segmentation).

This deep neural network achieves **~0.57 score on the leaderboard** based on test images,
and can be a good starting point for further, more serious approaches.

The architecture was inspired by [U-Net: Convolutional Networks for Biomedical Image Segmentation](http://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/).

## How to use

### Dependencies

This tutorial depends on the following libraries:

* scikit-image
* Tensorflow
* Keras >= 2.0

Also, this code should be compatible with Python versions 2.7-3.5.

### Prepare the data

In order to extract raw images and save them to *.npy* files,
you should first prepare its structure. Make sure that ```raw``` dir is located in the root of this project.
Also, the tree of ```raw``` dir must be like:

```
-raw
 |
 ---- train
 |    |
 |    ---- 1_1.tif
 |    |
 |    ---- …
 |
 ---- test
      |
      ---- 1.tif
      |
      ---- …
```

* Now run ```python data.py```.

Running this script will create train and test images and save them to **.npy** files.

### Define the model

* Check out ```get_unet()``` in ```train.py``` to modify the model, optimizer and loss function.

### Train the model and generate masks for test images

* Run ```python train.py``` to train the model.

Check out ```train_predict()``` to modify the number of iterations (epochs), batch size, etc.

After this script finishes, in ```imgs_mask_test.npy``` masks for corresponding images in ```imgs_test.npy```
should be generated. I suggest you examine these masks for getting further insight of your model's performance.
