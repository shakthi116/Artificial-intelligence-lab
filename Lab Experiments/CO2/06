# Feed Forward Neural Network

import numpy as np

# Input data (XOR problem)
X = np.array([
    [0, 0],
    [0, 1],
    [1, 0],
    [1, 1]
])

# Target output
Y = np.array([
    [0],
    [1],
    [1],
    [0]
])

# Sigmoid activation function
def sigmoid(x):
    return 1 / (1 + np.exp(-x))

# Initialize weights and biases
np.random.seed(1)

W1 = np.random.randn(2, 2)
B1 = np.zeros((1, 2))

W2 = np.random.randn(2, 1)
B2 = np.zeros((1, 1))

# Feed Forward
hidden_input = np.dot(X, W1) + B1
hidden_output = sigmoid(hidden_input)

output_input = np.dot(hidden_output, W2) + B2
output = sigmoid(output_input)

# Display results
print("Input:")
print(X)

print("\nActual Output:")
print(Y)

print("\nPredicted Output:")
print(np.round(output, 3))
