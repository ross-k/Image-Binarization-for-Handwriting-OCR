# Image-Binarization-for-Handwriting-OCR
This project takes the first step toward Optical Character Recognition for handwriting.  That step is using image binarization to distinguish foreground (text) from background (writing surface) in scanned images.  We want to see how well an artificial intelligence can predict which pixels will turn out to be text and which pixels will turn out to be background surface.

This begins by taking the 2016 and 2017 image data from the Handwritten Document Image Binarization Contest (H-DIBCO) and reading it into OpenCV in Python for training.  

We then take two different approaches to predicting image output.

First, we use a simple binary threshold approach in OpenCV.

Second, we use a Convolutional Neural Network in Keras.  This network is based on the one described in "A selectional auto-encoder approach for document image binarization" by Jorge Calvo-Zaragoza and Antonio-Javier Gallego in Pattern Recognition (DOI: 10.1016/j.patcog.2018.08.011 - see https://arxiv.org/pdf/1706.10241.pdf and https://github.com/ajgallego/document-image-binarization).

This network has ...< TO DO >

Success here is measured with an f1 score.  We choose this measurement because handwritten images are imbalanced data, in that there is much more background surface than there is text.  Also, we care much more about preserving the text data than we do about the background surface.  Therefore, we want to penalize false negatives, such that we do not falsely predict blank space when we should be seeing text.

f1 scores are as follows ...< TO DO (INSERT TABLE) >
