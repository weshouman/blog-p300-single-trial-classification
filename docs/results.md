# Results

---

## Single Trial Signal

By reducing the number of trials to one, the accuracy of the detected signal drops significantly which imposes a challenge in correctly classifying from a single trial

## Number of Trials

By varying the number of trials we find that even when PCA-based approach had an increase of `~2%` when the number of trials was high (15 trials), the approach in this paper excels by `~8%` in the single trial, and `~5%` for 5 trials

## Number of channels in classification

Having more channels (14 channels) in comparison with the 4 selected channels for classification in the proposed approach resulted in a decrease in the results by `~13%`, even when the increase of channels resulted in an increase of `~7%` 

## Activation Function

Linear activation exceled over the Logistic Sigmoid activation (by `~16%`) and over the Positive Saturating Linear function (by `~11%`)

## Hidden Layer Size of Stacked Autoencoders

Multiple sizes of the autoencoders in the hidden layers were used, and the highest accuracy of them are the one that gradually decreases in number over layers, until it reaches the bottleneck, showing enhancements up to `11%`

## Conclusion

Results obtained from introducing a stacked autoencoder deep learning technique for P300 speller show a noticeable increase in classifying single trials over the PCA-based methods.

The work could be extended by usage of:

- Convolutional Neural Networks could be considered.
- Variational autoencoders and comparing its performance with the different stack size selections.
