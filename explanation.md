# 📘 Conceptual Explanation of the Neural Network Code

This document explains how the Python code in `neuralnetwork.ipynb` mirrors the structure and logic of a basic feedforward neural network.

---

## 🔷 Network Architecture

- **Input layer:** 3 inputs
- **Hidden layer:** 4 neurons
- **Output layer:** 1 neuron

[3 inputs] → [4 hidden units] → [1 output]---

## 🧠 Key Concepts in the Code

### 1. Weight Matrices
syn0 = 2 * np.random.random((3, 4)) - 1
syn1 = 2 * np.random.random((4, 1)) - 1

-Represent the connections between layers.
-Randomly initialized and updated via training.


### 2. Forward Propagation
l1 = sigmoid(np.dot(X, syn0))
l2 = sigmoid(np.dot(l1, syn1))

-Input is passed through the layers using matrix multiplication and the sigmoid function.
-Produces predictions (l2).

### 3. Error and Backpropagation

l2_error = y - l2
l2_delta = l2_error * sigmoid_derivative(l2)
l1_error = l2_delta.dot(syn1.T)
l1_delta = l1_error * sigmoid_derivative(l1)

-Error is calculated at the output layer and propagated backward.
-Sigmoid derivative is used to calculate how much to adjust weights.

### 4. Weight Updates

syn1 += l1.T.dot(l2_delta)
syn0 += X.T.dot(l1_delta)

Gradients are applied to update the weights and improve the predictions.

| Element                | Code Equivalent               | Role in Neural Networks                        |
| ---------------------- | ----------------------------- | ---------------------------------------------- |
| Neurons                | Each row in `l1` or `l2`      | Process information and pass signals           |
| Synapses (connections) | `syn0` and `syn1`             | Carry weighted signals between layers          |
| Activation function    | `sigmoid` (1 / (1 + exp(-x))) | Adds non-linearity and decision-making ability |
| Forward propagation    | `np.dot(...)` + sigmoid       | Compute outputs from inputs                    |
| Error signal           | `y - l2`                      | Tells how far off the prediction is            |
| Backpropagation        | `delta` calculations          | Adjusts internal weights based on error        |
| Learning               | `+=` to update `syn0`, `syn1` | Minimizes error over time                      |
