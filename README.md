# CarvanaSegmentation
This is my learning progress on carvana image segmentation challenge.

carvana_exploration.ipynb - trains a basic TernausNet with a pretrained VGG11 encoder across 4 folds. 
carvana_prediction_loop.ipynb- generates the output masks for multiple images.

# Observations
We observe that certain generated masks contain "Grey" regions or "White" portions in the holes of the car tires. This is due to incorrect segmentation masks present in the original dataset. We evaluate the unconfidence interval of this network and find it to lie in the range [0.3,0.7]. 

# Results

The images folder contains some of the positive results where our model performs well and some negative results where the model predictions are associated with high variance. 

# Future Work

An ensemble of TernausNet with LinkNet had ranked 1st in the Carvana Image segmentation challenge. As science progresses, this can now only reach (top 50) positions on Kaggle leaderboard (beneath baselines).

Latest competitions [TGS salt Identification challenges] involve the various approaches:
A) Squeeze and Excitation networks in the encoder portion of the UNets (Check ArXIV paper).
B) Cutout in input images instead of dropout to increase model robustness. 
C) It was found that a BCE Loss containing a Dice metric is non differentiable. Therefore, an alternate approach has been to approximate the bounds with a convex Lovasz Loss. The winners extended the approach to something called "Symmetric Lovasz Loss" which I hope to explore in the future.

