# LiDeRe Reproduction Project

This repository holds my one week project for the Beihang University computer vision group. I reproduce a CVPR 2026 paper and test it on new data.

## The paper

LiDeRe: A Lightweight Readout for Fast and Data Efficient Dense Prediction
Authors: Timo Luddecke and colleagues (University of Goettingen)
Venue: CVPR 2026
Official code: https://github.com/timojl/lidere

The idea is simple. A large pretrained vision model stays frozen. Only a tiny readout on top of it is trained. Training is fast and it works with very few labeled images.

## What is in this repository

The lidere folder and the files in the main folder come from the authors. They are their official code. My own work is here:

1. experiments holds my notebooks
2. results holds my numbers and pictures
3. reports holds the final report
4. LOG.md holds my daily work log

## What I did

1. Ran the authors inference demo on a Kaggle GPU
2. Trained the readout on the four example images from the authors
3. Reproduced the Leaf Disease Segmentation experiment (399 training and 90 test images)
4. Tested the method on a small remote sensing dataset with only a few labeled images (planned)

## Results

Leaf Disease Segmentation
Paper result: to be added
My result: to be added

Remote sensing experiment: to be added

## How to run

1. Open a Kaggle notebook and turn on the GPU and internet
2. Clone the authors code: git clone https://github.com/timojl/lidere
3. Download the Leaf data from https://automl-mm-bench.s3.amazonaws.com/semantic_segmentation/leaf_disease_segmentation.zip and unzip it into a folder called data
4. Set the DATA_ROOT variable to that data folder
5. Open the notebook in the experiments folder and run the cells in order

## Differences from the paper

1. I used a ViT B backbone because it fits on a free GPU
2. Images are resized to 512 pixels
3. I trained for 500 steps with batch size 16
4. Weight decay is 0 because the authors code uses 0

## Credits

All credit for the method and the code goes to the original authors. Their code uses the MIT license. The model weights have their own license.