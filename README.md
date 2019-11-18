# CarvanaSegmentation
This is my learning progress on carvana image segmentation challenge.

carvana_exploration.ipynb trains a basic TernausNet with a pretrained VGG11 encoder across 4 folds. 
carvana_prediction_loop.ipynb generates the output masks for multiple images.

# Observations
We observe that certain generated masks contain "Grey" regions or "White" portions in the holes of the car tires. This is due to incorrect segmentation masks present in the original dataset. We evaluate the unconfidence interval of this network and find it to lie in the range [0.3,0.7]. 
