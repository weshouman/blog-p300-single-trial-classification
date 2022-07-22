# Results

---

The paper shows results for the following scenarios.

Graphs for the different results could be found in the paper directly, only a description of the results are mentioned in this documentation.

## Single Trial Signal

By varying the number of trials made per each character recognition, we change the difficulty of recognizing the P300 signal from non-P300 signal, thus reducing the 15 trials, to 5 trials and to 1 trial imposes a great challenge in correctly classifying the signal from a single trial. 

## Number of Trials

Comparing the paper's approach with the previous approach (PCA based) over the different trials the following results are found:

- For 15 trials: the current approach falls behind by `~2%`
- For 5 trials: the current approach excels by `~5%`
- For a single trial: the current approach excels by `~8%`

## Number of channels in classification

Through out the data acquisition phase only 4 selected channels were used, in this result section the results from 14 channels is compared to the 4 channels:

- The previous approach increased by `~7%` when the 14 channels were used
- The current approach decreased by `~7%` when the 14 channels were used

In general, the average accuracy for the previous approach for the 14 channels are the same as the average accuracy for the current approach for the 4 channels only

## Activation Function

As mentioned in the [feature extraction section](methodology.md#autoencoders), multiple activation functions could be used, following are the results of using those functions:

Linear activation exceled over the Logistic Sigmoid activation (by `~16%`) and over the Positive Saturating Linear function (by `~11%`)

- Linear activation resulted in `~54%` accuracy
- Linear activation exceled over the Logistic Sigmoid activation (by `~16%`)
- Linear activation exceled over the Positive Saturating Linear function (by `~11%`)

## Hidden Layer Size of Stacked Autoencoders

As mentioned in the [feature extraction section](methodology.md#autoencoders), an autoencoder could have stacked hidden layers to reach the bottleneck, following are the results of varying the number of hidden layers:

- Gradually decreasing number of hidden layers had an accuracy of `~54%`
- Gradually decreasing number of hidden layers after an initial increase had an accuracy of `~43%`
- Constantly decreasing number of hidden layers had an accuracy of `~50%`
- Constantly and aggressively decreasing number of hidden layers had an accuracy of `~45%`

## Conclusion

Results obtained from introducing a stacked autoencoder deep learning technique for P300 speller show a noticeable increase in classifying single trials over previous approach mentioned at the paper [A Principal Component Analysis Ensemble Classifier for P300 Speller Applications](https://ieeexplore.ieee.org/document/6703782).

The work could be extended by usage of:

- Convolutional Neural Networks could be considered.
- Variational autoencoders and comparing its performance with the different stack size selections.
