this repo is for our first writting trail 
we have managed to use genetic algorithm ga in matlab to find the optimum trimming
neural network hyperparameters 

our matlab  function optimizeNNForTrimmingPumpImpeller(QH-matrix,D_eta-matrix) takes in two arguments the


QH-matrix which is the input to the neural network

D_eta-matrix which is the output

our training dataset is in this excel file originaly centrifugal-pump-dab-2900-rpm-90-m-head-data.xlsx 

and you could use it directly in matlab via load('trimming_nn_training_dataset.mat')
this will load two vars to matlab :
1. QH_nn_input
2. D_eta_nn_output

to find the optimum architecture call optimizeNNForTrimmingPumpImpeller(QH_nn_input',D_eta_nn_output')

**please make sure you do the transpose **


it returns :  [optimalHyperParams, finalMSE, randomSeed, bestTrainedNet] 

where the bestTrainedNet is the trained net object provided by matlab


To export a trained neural network as a function version, you can use the genFunction:

genFunction(trainedNet, 'trainedNetworkFunction');

where trainedNetworkFunction is just a name for the file that would be created by the matlab 