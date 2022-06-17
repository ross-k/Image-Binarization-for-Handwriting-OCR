              # Image-Binarization-for-Handwriting-OCR


# The Inspiration for This Concept

The world is full of old handwritten documents that give us a priceless connection with history. The more that the world changes, the more valuable this connection becomes.

However, many historical documents are hidden in library archives that are too far away for researchers to travel. Libraries tend not to circulate or share these documents, since they are fragile.

Scanning these documents would let more people access them, learn from them and enjoy them, without exposing the documents to damage and requiring people to make long research trips.


# The Scope of the Current Project

The current project does not attempt the transcription and translation of scanned document images.  Instead, it sets the stage for those later steps by processing the image scans into a format that lets computers read the document text more easily.

Once they have been scanned and put online, it would add even more value to transcribe these documents automatically using artificial intelligence. AI might even be able to translate them. This could speed up collaborative research by streamlining some of the most time-consuming parts of scholars' jobs.

This project takes the first step toward Optical Character Recognition for handwriting.  That step is using image binarization to distinguish foreground (text) from background (writing surface) in scanned images.  We want to see how well an artificial intelligence can predict which pixels will turn out to be text and which pixels will turn out to be background surface.


# Steps

This begins by taking the 2016 and 2017 image data from the Handwritten Document Image Binarization Contest (H-DIBCO) and reading it into OpenCV in Python for training.  

We then take two different approaches to predicting image output.

First, we use a simple binary threshold approach in OpenCV.

Second, we use a Convolutional Neural Network in Keras.  This network is based on the one described in "A selectional auto-encoder approach for document image binarization" by Jorge Calvo-Zaragoza and Antonio-Javier Gallego in Pattern Recognition (DOI: 10.1016/j.patcog.2018.08.011 - see https://arxiv.org/pdf/1706.10241.pdf and https://github.com/ajgallego/document-image-binarization).

Success here is measured with an f1 score.  We choose this measurement because handwritten images are imbalanced data, in that there is much more background surface than there is text.  Also, we care much more about preserving the text data than we do about the background surface.  Therefore, we want to penalize false negatives, such that we do not falsely predict blank space when we should be seeing text.

Findings from the data used are as follows: f1 score decreases slightly with more training data added for the thresholding approach, while it increases slightly with more training data added when using a convolutional neural network.  The optimum configuration out of those tried here used 3 network layers with 3 x 3 kernels and image window sizes of 128 pixels.


# The Impact of This Work

It is hoped that automatic transcription and translation of handwritten documents would reduce the cost and potential downside of viewing them and allow greater informational exchange across borders, cultures and languages than humanity has ever had.

This could have a revolutionary effect on the availability of historical, linguistic and literary resources to students and researchers worldwide.
