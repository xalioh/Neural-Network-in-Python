# 🧠 Neural Network from Scratch in Python

This project demonstrates a minimal working implementation of a feedforward neural network using just **NumPy**. It’s designed for learners who want to understand the core logic of forward propagation, backpropagation, and weight updates—without relying on machine learning libraries like TensorFlow or PyTorch.

## 📁 Files
- `neuralnetwork.ipynb` – Jupyter Notebook with fully commented Python code
- `explanation.md` – A written explanation of how the code works and how it simulates a real neural network

## 🚀 Features
- 1 hidden layer (4 neurons)
- Binary classification task
- Sigmoid activation
- Manual weight updates using gradient descent
- Trains on XOR-style logic pattern

## 🧰 Requirements
- Python 3.x
- NumPy
- Jupyter Notebook

## ✅ Output
The network should correctly learn the target output:
Input: [0,0,1] → Prediction: ~0
Input: [0,1,1] → Prediction: ~1
Input: [1,0,1] → Prediction: ~1
Input: [1,1,1] → Prediction: ~0

### 📖 Learning Goals

Understand:
- The role of weights, layers, and activation functions
- How forward propagation generates predictions
- How backpropagation corrects those predictions