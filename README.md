** MoNuSAC Challenge Approach By Group 3 As Part Of The Seminar Maschinelles Lernen **

Our Finall Result is the Pyramid-Net.ipynb so we will explain here how this works (the U-Net works the same).

First of all you will need the MoNuSAC dataset from their website.
Then you need to run the Binary_mask_generation.ipynb which is created by Ruchika Verma to extract the masks for each image in the dataset.
After that you can Run the FPN or the U-net with these data set you may only need to change the Paths but that is explained in the FPN itself.
And finally you can run the PQ_metric_new.ipynb to see how good our PQ metric is.