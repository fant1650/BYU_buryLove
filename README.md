# BYU_buryLove
## About this project
### Hello!We are a team named "塟❤の⺗惩什".This is a feasible solution to "BYU - Locating Bacterial Flagellar Motors 2025", which is a competition hold by Brigham Young University on Kaggle.Below are the content of this competition and the description of our solution

## Overview
#### The goal of this competition is to develop an algorithm to identify the presence and location of flagellar motors in 3D reconstructions of bacteria. Automating this traditionally manual task will accelerate the study of macromolecular complexes, which helps answer fundamental questions in molecular biology, improve drug development, and advance synthetic biology.

## Description
#### The flagellar motor is a molecular machine that facilitates the motility of many microorganisms, playing a key role in processes ranging from chemotaxis to pathogenesis. Cryogenic electron tomography (cryo-ET) has enabled us to image these nanomachines in
near-native conditions. But identifying flagellar motors in these three-dimensional reconstructions (tomograms) is labor intensive. Factors such as a low signal-to-noise ratio, variable motor orientations, and the complexity of crowded intracellular environments complicate automated identification. Cryo-ET studies become limited by the bottle-neck of a human in the loop. In this contest, your task is to develop an image processing algorithm that identifies the location of a flagellar motor, if it is present.

A tomogram is a three-dimensional image that has been reconstructed from a series of 2D projection images. The images in this challenge are tomograms of bacteria that have been flash-frozen in ice, which preserves the molecular structure of the bacteria for the imaging process. This video walks through slices of a tomogram highlighting different features of a bacterial cell, including a flagellar motor. The accompanying text describes the purpose and function of the motor.

## Evaluation
### Evaluation Metric
#### Submissions will be evaluated using a combination of the Fβ
-score and Euclidean distance. The goal is to determine whether a tomogram contains a motor and, if it does, to accurately predict its location.

Let the ground truth be y
 and the predicted location be y¯
. The Euclidean distance |y−y¯|2
 determines classification:
- True Positive (TP): If |y−y¯|2≤τ
, the prediction is within threshold.
- False Negative (FN): If |y−y¯|2>τ
, the prediction is outside of threshold.
where  τ=1000
 Angstroms.
### Fβ-score
#### The Fβ-score balances precision and recall, placing greater weight on recall when β>1
 and on precision when β<1
 (in our case we use β=2
, thus we are weighting recall more than precision). It is defined as:

Fβ=(1+β2)⋅precision⋅recall(β2⋅precision)+recall=(1+β2)⋅TP(1+β2)⋅TP+β2⋅FN+FP

This metric ensures that both the presence and location accuracy of predicted motors are considered in the final score.


