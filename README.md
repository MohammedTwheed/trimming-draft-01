

---

# Impeller Trimming Optimization


## Paper website

here you can find our very first draft where we try to explain
the process in more depth  you can download it as **pdf** or **word**:


[**click here to get our paper first draft**](https://mohammedtwheed.github.io/trimming-draft-01/)

Welcome to the Impeller Trimming Optimization repository! This project showcases our efforts to utilize a genetic algorithm (GA) in MATLAB to optimize neural network hyperparameters for the purpose of impeller trimming. This approach aims to enhance the performance of pump impellers through data-driven optimization techniques.

## Project Overview

In this project, we use MATLAB's genetic algorithm capabilities to optimize the hyperparameters of a neural network for the task of impeller trimming. The goal is to improve the efficiency and performance of pump impellers by adjusting their geometry based on predictions from the neural network.

## Function: `optimizeNNForTrimmingPumpImpeller(QH_matrix, D_eta_matrix)`

The main function in this project is `optimizeNNForTrimmingPumpImpeller`, which takes in two arguments:

- `QH_matrix`: The input matrix to the neural network representing the features.
- `D_eta_matrix`: The output matrix representing the targets for the neural network.

## Dataset

The training dataset for the neural network is provided in an Excel file:

- File: `centrifugal-pump-dab-2900-rpm-90-m-head-data.xlsx`
- Alternatively, you can load the dataset directly in MATLAB using:
  ```matlab
  load('trimming_nn_training_dataset.mat')
  ```

This will load two variables:

- `QH_nn_input`
- `D_eta_nn_output`

To use the `optimizeNNForTrimmingPumpImpeller` function, ensure you transpose the input data:

```matlab
optimizeNNForTrimmingPumpImpeller(QH_nn_input', D_eta_nn_output')
```

## Function Output

The function `optimizeNNForTrimmingPumpImpeller` returns the following outputs:

- `optimalHyperParams`: The optimized hyperparameters for the neural network.
- `finalMSE`: The final mean squared error of the best model.
- `randomSeed`: The random seed used for reproducibility.
- `bestTrainedNet`: The best trained neural network object.

## Exporting Trained Neural Network

You can export the best trained neural network as a function using the `genFunction` function in MATLAB:

```matlab
genFunction(bestTrainedNet, 'trainedNetworkFunction');
```

This will generate a function version of the trained network and save it to a file named `trainedNetworkFunction.m`.

## Usage

To get started with the project, clone the repository and load the provided dataset. Run the `optimizeNNForTrimmingPumpImpeller` function with the input and output matrices as described. The function will return the optimized hyperparameters and other related results.

Happy coding and optimizing! If you have any questions or feedback, feel free to open an issue in the repository.

---