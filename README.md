# Overview

This Jupyter Notebook contains code for augmenting a dataset and training a PyTorch model to arrange text blocks in the correct order. The goal of the model is to determine the sequential arrangement of text blocks based on their spatial positions after individual words in a document have been recognized and grouped.

## How It Works

The model is provided with the coordinates of each text block and iteratively determines the correct order by selecting the first block at each step.
After a block is selected, it is removed from the list, and the procedure is repeated until no blocks are left.
This approach ensures that the text blocks are arranged in a coherent reading order.

## Data Requirements

The dataset should be uploaded to the text_blocks_locations folder.
Each document in the dataset should be represented as a separate JSON file containing a list of blocks, where each block is defined by its four corner coordinates:
'''
[
{ "x1": 67.13, "y1": 96, "x2": 790.13, "y2": 174 },
{ "x1": 41, "y1": 201, "x2": 791, "y2": 466 }, 
{ "x1": 50.5, "y1": 492, "x2": 753.5, "y2": 537 }, 
{ "x1": 41, "y1": 555, "x2": 791, "y2": 757 },
{ "x1": 41, "y1": 783, "x2": 791, "y2": 1048 }
]
'''

Here, each block is represented by its four coordinates: (x1, y1) and (x2, y2), denoting the top-left and bottom-right corners, respectively.

## Data Augmentation 

Once the data is uploaded, it undergoes augmentation by rotating each document at different angles.
The text blocks within each document are also split into varying chunks to simulate diverse layouts and arrangements.
This augmentation process helps the model generalize better to different document structures, making it more robust in real-world applications.

