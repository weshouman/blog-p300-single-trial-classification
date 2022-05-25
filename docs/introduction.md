# Introduction

---

!!! Important "Goal of the paper"
    The goal of the paper is to investigate the deep learning approach in achieving a higher accuracy while communicating the desired characters with the P300 speller from as little as a single trial.

Brain Computer Interface (BCI) technology could enable communication with individuals with server motor disabilities, by communicating directly with the brain signals.  

To achieve BCI, one needs to determine:

1. How the electrods are to be placed
2. Which brain activity to be considered
3. Which computer program to use
4. Which learning technique to use

In this introduction we clarify the context that this paper working on.

## Electrode Placement

To make a BCI, one needs to place electrodes onto the individual's head, the are 3 ways to achieve such placement: non-invasive, semi-invasive and invasive, the following figure and table illustrate that further:

<figure markdown>
  ![Different BCI electrodes](https://images.squarespace-cdn.com/content/v1/58fd278d6a49633370c4ebbe/1493702709246-R1PH4JYCON3WPUNP7ZZM/image-asset.png){width="200"}
  <figcaption><a href="https://www.bmseed.com/stretchable-electrodes-for-brain-implants">Different BCI electrode placements [1]</a></figcaption>
</figure>


| Method      | Non-Invasive  | Semi-Invasive | Non-Invasive |
| ----------- | --------------|------------|------- |
| Recorded brain activity | Electroencephalographic (EEG) | Electrocorticography (ECoG) | Individual neurons |
| Electrode placement     | Over the head | Over the brain | Inside the brain |
| Surgical operation      | Not required | Required | Required |
| Spatial Resolution      | Least | Medium | High |

!!! Note "Paper Approach"
    This paper investigates the usage of EEG based activities.

## P300 Speller

<figure markdown>
  ![P300 speller](https://www.researchgate.net/publication/311359887/figure/fig2/AS:682065372643328@1539628465050/Stimulus-and-operating-principle-of-P300-speller-When-the-subject-counts-the-number-of.ppm){width="400"}
  <figcaption><a href="https://www.researchgate.net/figure/Stimulus-and-operating-principle-of-P300-speller-When-the-subject-counts-the-number-of_fig2_311359887">Time diagram of a P300 speller [10]</a></figcaption>
</figure>

The computer program used for the interface is a P300 speller which works by showing the user a MxN matrix of the characters of interest (6x6 matrix for this paper) and flashing each row and column for K times (called K trials), for example if K is 1 (single trial) there will be 12 flashes (6 different row flashes and 6 different column flashes), K is 5 (5 trials) there will be 60 flashes (30 row flashes and 30 column flashes).  

The flashes occur randomly and have Interintisification Intervals (ISI) of 100 ms between them.  

The user needs to focus on the character he wants to type each time, and once the screen flashes in front of him a brain activity shall evoke after 300 milliseconds which could be detected to figure out that the character the user is looking at is in the flashed row or column, 300 ms ago.  

Increasing the number of trials, would increase the detection accuracy, however each extra trial involves extra 12 flashes. 

!!! Note "Paper Approach"
    This paper utilizes the reads P300 brain activitiy, and uses the P300 speller as the software for interaction.  
    It also observes the effect of the deep learning approach on the decrease of the trials.

## Learning Techniques

<figure markdown>
  ![Neural Network image](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Colored_neural_network.svg/1024px-Colored_neural_network.svg.png){width="200"}
  <figcaption><a href="https://en.wikipedia.org/wiki/Artificial_neural_network">Artificial Neural Network [14]</a></figcaption>
</figure>

To learn from the brain activities both feature extraction and classification shall be utilized. There are multiple techniques for doing so.
The classification problem in hand is considered a supervised learning one, as the classes are pre-known `{P300 and non-P300}`.

Different approaches could be considered to learn the model, for example Principal Component Analysis (PCA), Linear Discriminant Analysis (LDA), Independent Componant Analysis (ICA), autoencoders, Fisher's Linear Discriminant Classifier, Maximum Likelihood Discriminant Classifier KNN, etc.

!!! Note "Paper Approach"
    This paper addresses the deep learning technique for the model, namely using stacked autoencoders with softmax *a differentiable version of argmax*, to learn the data compared to the usage of Principal Component Analysis (PCA) and Linear Discriminant Analysis (LDA) in previous models.
