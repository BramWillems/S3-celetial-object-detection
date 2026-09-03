# Detecting Objects in Astronomical Images

Automatically detecting interesting objects (galaxies, nebulae, star clusters)
in amateur telescope images, so hobbyist astronomers can tell if they've
captured something worth a closer look.

## The problem

Imagine looking through a telescope for the first time. What are you actually
looking at? Is there anything interesting in the image? Without experience,
it's hard to tell. This project trains a model to answer that question
automatically from a home-made telescope image.

## Result

![Model comparison](https://github.com/BramWillems/S3-celetial-object-detection/blob/main/comparison.jpg)

The first version of the model reached about 65% detection accuracy, with
roughly 75% of detected objects having mostly correct bounding boxes. After
fixing data issues (see below) and using a larger model with tuned
hyperparameters, performance improved by about 10%.

## Data

The dataset (from the [MILAN research project](https://zenodo.org/records/8387071))
contains 4096 images pre-labeled in YOLO format, covering emission/reflection/dark/
planetary nebulae, galaxies, and globular/open clusters. The images are 608x608
patches cut from larger telescope captures taken across Europe.

One issue in the raw data: some objects were cut off at the patch edges,
which hurt training. I wrote a function to check bounding box size and
distance from the edge, then manually reviewed and cleaned flagged cases.

## Method

- Trained a YOLO object detection model (pre-built architecture, fine-tuned
  on this dataset)
- Compared multiple YOLO model sizes and selected the best-performing one
- Checked inference speed across different devices to confirm the model is
  practical to run outside a training environment

## Skills used

Python (Jupyter notebooks), image data cleaning and reorganization,
extracting data from images, training and evaluating YOLO models

## What I learned

How to work with and fine-tune a pre-trained model, and how to extract and
manage data derived directly from images rather than a clean tabular source.
