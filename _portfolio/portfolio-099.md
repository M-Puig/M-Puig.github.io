---
title: "Deep Neural Networks Calibration - ONERA - 2021"
excerpt: "<img src='/images/ONERA-logo.svg' width=200>"
collection: portfolio
---

Neural networks usually output uncalibrated scores, called logits, that are then normalized into probabilities using a softmax in the multiclass case, or a logistic function in the binary case. These probabilities are quite often used as the likelihoods of the input belonging to each of the output classes. For instance, if an image has an output probability of 0.9 to belong to the class "Cat", then it can be interpreted as having a 90% chance of picturing a cat. However, deep neural networks tend to be overconfident, that is, to output probabilities higher than its actual confidence in the prediction. In critical applications, for instance in domains such as healthcare or aerospace, it is of utmost important to have a precise idea of the confidence level of the network's prediction.

This discrepancy can be observed in this example Reliability diagram. In a perfectly calibrated network, the predictions should follow the identity line.
<img src='/images/ex_confidencediag.png' width=400>

My task was to research calibration methods in the litterature, implement them and compare them. To do so, I proposed a framework using synthetic data and bayesian probabilities to benchmark the different techniques and evaluate them under different conditions, and with various metrics, the most important one being the Expected Calibration Error (ECE).