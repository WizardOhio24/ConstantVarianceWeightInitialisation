# <c> Constant Variance Weight Initialisation </c>

This repo houses the code for the paper Constant Variance Weight Initialisation.

## Abstract
Weight initialisation is a necessary first step in all neural networks: This work reviews the currently popular methods of weight initialisation without using input data and proposes Constant Variance Weight Initialisation. Applied to small neural networks, Constant Variance initialisation is shown to result in an increase in training speed compared to Xavier initialisation, a result which fails to generalise to larger neural networks. However, equivalent performance can be achieved on larger neural networks either by scaling the range of the S-shaped activation function or by reducing the standard deviation of the input and the standard deviation of the forward propagation. Constant Variance initialisation is then compared to He initialisation, where it shows no significant difference in training speed when applied to small neural networks, but results in an improved training speed when applied to larger neural networks.


## Prerequisties

A python environment with jupyter notebook is required.
Below are the libraries used in this project (See `requirements.txt` for exact requirements):
 - PyTorch
   - Torch
   - Torchvision
 - numpy
 - matplotlib
 - scikit-learn (sklearn)
 - pillow


## Running
The code has two main parts, generating the activation function coefficients, 
and testing the activation function coefficients on the chosen problems.

First, to generate the activation function coefficients:
 - Run the `ActivationCoefficients.ipynb` notebook

This generates two files, `coeffs.csv` and `coeffs_uniform.csv` which contain the coefficients used when applying constant variance weight initialisation for each activation function.

After this, the results can be generated by running:
 - `XavierFashionMNIST.ipynb` | Section 3.1
   - Constant Variance compared to Xavier Initialisation applied to the FashionMNIST dataset
 - `CIFARClassification.ipynb` | Section 3.2
   - Constant Variance compared to Xavier initialisation applied to the CIFAR dataset.
 - `HeFashionMNIST.ipynb` | Section 4.1
   - Constant Variance compared to He initialisation applied to the FashionMNIST dataset.
 - `ReLUCIFARClassification.ipynb` | Section 4.2
   - Constant Variance compared to He initialisation applied to the CIFAR dataset.

This will put the results in four different folders which must exist before running the code.  These folders containing the raw results are provided in this repository.  Respectively these folders are:
 - `XavierFashionMNIST_test`
 - `XavierCIFAR_test`
 - `HeConstVarFashionMNIST_test`
 - `HeCIFAR_test`

Generating the plots/figures based on these experiments are mostly included in the same notebook.  There are two additional notebooks for plotting some results:
 - `ReLUCIFARPlotter2.ipynb` | Figure 6
   - Plots the results for Constant Variance initialisation compared to He initialisation.
 - `XavierComparason5.ipynb` | Figure 3
   - Plots the forward propagated variance on each layer

The generated plots/figures have also been included in the `PaperImages` folder.

