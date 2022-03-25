# Support Vector Machine
Supervised. Given 2 or more labeled classes of data, it acts as a discriminative classifier, formally defined by an optimal hyperplane (e.g : a line if two classes) that separates all the classes. New examples that are then mapped into that same space can then be categorized based on which side of the gap they fall.
The hyperplane is computed to maximize the distance between the hyperplane and the support vectors (the points in the datasets that are closest to the hyperplane).
If we remove the support vectors, the hyperplane would be altered. The hyperplane is N-1 dimensionned, with N the number of classes.
SVM can deal with non-linear classification using the kernel trick.

## Loss function, objective function
x: sample, y: label (-1 or +1), f(x) : predicted label, <x<sub>i</sub>,w> : predicted label (other notation), &lambda; : regularizer = 1/epoch

Binary Hinge loss (it can be upgraded to multiclassification) : c(x,y,f(x)) =  (1-y * f(x))<sup>+</sup>

Objective function : min<sub>w</sub> &lambda;||w||<sup>2</sup> + &Sigma;<sub>i=1</sub><sup>n</sup> (1-y<sub>i</sub> <x<sub>i</sub>,w>)<sub>+</sub>

It consists of two terms. The first term is a regularizer, avoid overfitting and making sure the model generalizes well to new data, the second term the loss. The regularizer balances between margin maximization and loss. We want to find the decision surface that is maximally far away from any data points.

## Weight update
Computed from gradient descent (derivatives of the objective function)

&eta; : learning rate = 1, &lambda; : regularizer = 1/epoch

w = w + &eta; (y<sub>i</sub> x<sub>i</sub> - 2 &lambda; w)

## Use cases
Great with small datasets ! <1000 data points

* Mainly: classification

* To a lesser extent : regression (time serie prediction, etc), outlier detection, clustering

## Libraries

* This project has a SVM algorithm built from scratch
* scikit-learn has a built-in SVM algorithm

## Git examples

* Classify images with scikit-learn : https://github.com/ksopyla/svm_mnist_digit_classification
* Pulse classification, more useful dataset : https://github.com/akasantony/pulse-classification-svm

## Credits

* Siraj Raval
* Disclaimer : Code is used as an illustration of the README theory file. Code has been forked from [maviccprp](https://github.com/MaviccPRP/svm/blob/master/svm-primal.ipynb). I mainly corrected/updated it to make it work on my computers.
* https://sites.psu.edu/symbolcodes/codehtml/#math
