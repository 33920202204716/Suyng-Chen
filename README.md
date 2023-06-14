## Peptide Learning and Prediction
### Preparation
Pep2Smiles can achieve the following targets: convert peptide to its smiles format, generating data file for CMFV3.1.
### Characterization
CMFV3.1 is used to characterize the molecule from smiles to digits that can be learned by the computer. The method includes one-hot encoding, molecular fragment, rdkit description, and peptide descriptors. Users can choose what to use when characterizing a molecule.
### Feature Selection
AFS-LF_V2.4-Beta-SHAP.ipynb is used to choose feature with the help of SHAP value based on game theory. It can give you the most important features in your feature list so that you can use them to train your model.
GBRT-Stepregression.ipynb is also used to choose features. What's different here is that the method used here is to choose feature once at a time through step regression, and it's easy to understand
### Train & Prediction
We use Gridsearch CV to optimize the hyperparams, and then based on the 10-fold split, we have trained 10 different models, which are used to predict the new sequence to get the mean and std of it. Once we can get the mean and std, we can then generate sequence randomly. Through mutation and cross-exchange, we can get generations and prediction the fitness of them. Fitness used here is based on Upper Confidence Boundary with different ungreedy factors. And the sequence will envolve from generation to generation, and finally I will get the best-performed sequence.
