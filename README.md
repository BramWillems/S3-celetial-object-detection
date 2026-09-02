# Detecting objects in astrological images

In this project the goal was to check astrological images if there is any of the marked objects, this is done to make it easier for hobbist astrologers without much knowledge yet to know if there are any interesting objects in the image they took with their telescope.

Let's assume you on a telescope, but this is your first time looking through it, hat are you looking at? Is there anything interesting? how would you know? This project is intented for this audience. In this project we take a reliable dataset (link to data) and use this to train a YOLO model to check if any of your home made images contain anything interesting, this could be a for example be galaxy, gas cloud or even reflections of this. After analyzing the dataset for outliers, this can for example be an image with a bounding box too small. We train a YOLO image recognition model, this model is a pre-built model that can be trained on image detection tasks. This model also had different sizes which are compared and the best one is chosen. At the end inference is checked to make sure this model can run on different devices.

skills: <br>
Python programming in jupyter notebook
editing and reorganising image data
Getting data out of images
YOLO image models training and evaluating
