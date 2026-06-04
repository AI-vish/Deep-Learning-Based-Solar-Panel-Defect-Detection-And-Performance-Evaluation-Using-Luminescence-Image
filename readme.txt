I have tried to include all the files I could recover from my project files,  I haven't included the result images of the final industrial dataset due to it huge size.

Steps

open source PVEL dataset
preprocessing (CLAHE+ NLM denoising+ morph closing+ unsharp masking)
resnet (split into good and defected images)
yolo (classify bad images into it's defect classes) (cracks, fingers, and thickline)
industrial dataset analysis and cleaning (edges removal, multicell img removal, multiple busbars removal)
correlational analysis (defect vs electrical parameter, and image derived parameters vs electrical parameters)
regression (image derived parameter and defect parameters were used as features) (don't use electrical paramenter to train the regression model)

I have also attached the ppt and final year thesis paper and conference paper

for conference paper we created a 3 split resnet model( split dataset into 3 batch) trained using 2 and testing using one , 3 such process was done to verify our results ( that files got missed)