# BHaND

The full form for BHaND is "Bengali Handwritten Numerals Dataset".

In this work we have created a new dataset containing images of handwritten Bengali numerals. Our main target in this work was to make the dataset similar to MNIST, one of the most famous English handwritten digit dataset.

Similar to MNIST, we have collected 70,000 sample images of Bengali digits, each image is 32*32 in size (MNIST images were 28*28 in size). Rest of everything are exactly similar to MNIST.

# Basic Description

1. This file has 70,000 samples divided into three sets namely the training set containing 50,000 samples, the validation set containing 10,000 samples and the test set containing 10,000 samples.
2. Each raw of these sets has two dimenstions, the first dimension is the image itself and the second dimesion is the label. Here label means which digit (0 to 9 in Bengali) this image represents. Thus the training set has 50,000 rows and two columns. Other sets are also similar in nature.
3. Each of the samples are in grayscale form normalized to the intensity range [0,1] and the intensity were inverted to make black pixels 1 and white pixels 0. The images were then reshaped to a single dimenstion making 1024(32*32) features in total. Thus the first dimension of each row in each set is a 1024 dimension vector and the second dimension of each row in each dataset is a regular integer number (0 to 9).
4. All these samples were then grouped together in a single pickle file using python's serializer cPickle, then they were compressed by GZIP compressio algorithm for faster transmission.

# How To use this dataset
You can use the following python code segments to use the dataset in your porject:

```
f = gzip.open('bhand.pkl.gz','rb')
trainSet,validSet,testSet = cPickle.load(f)
f.close()

trainSet_x, trainSet_y = trainSet
validSet_x,validSet_y = validSet
testSet_x,testSet_y = testSet
```
Now, in trainSet_x you have all 50,000 images (50000 rows, 1024 columns), in trainSet_y you have 50,000 corresponding labels (50000 rows, 1 columns). validSet and testSet are similar in nature.

# Conditions for using this dataset
To use this dataset in your own work, you are required to cite the below article:
```
Title: Towards optimal convolutional neural network parameters for bengali handwritten numerals recognition
Authors: Al Mehdi Saadat Chowdhury and M. Shahidur Rahman
DOI: 10.1109/ICCITECHN.2016.7860237 
WebLink: http://ieeexplore.ieee.org/document/7860237/
```

In Latex:
```
@inproceedings{saadat2016b,
    author =       "Al Mehdi Saadat Chowdhury and M. Shahidur Rahman",
    title =        "Towards optimal convolutional neural network parameters for Bengali handwritten numerals recognition",
    booktitle =	   "Proceedings of 19th International Conference on Computer and Information Technology (ICCIT)",
    pages = {431--436},
    year = {December 2016},
    address = "Dhaka"
    keywords =     "CNN"
}
```

Regular citation:
```
A. M. S. Chowdhury and M. S. Rahman, “Towards optimal convolutional neural network parameters for Bengali handwritten numerals recognition,” in proceedings of 19th International Conference on Computer and Information Technology (ICCIT), Dhaka, pp. 431-436, December 2016.
```

