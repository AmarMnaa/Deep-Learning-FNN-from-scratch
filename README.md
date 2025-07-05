# Deep-Learning-FNN-from-scratch
# Batch Size Optimization in Neural Networks

This project explores the impact of different batch sizes, batch normalization, and L2 regularization on training a neural network from scratch — without using deep learning libraries like PyTorch or TensorFlow.

## 🧠 Custom Neural Network Implementation

The core of this project is a fully connected feedforward neural network (FNN) **implemented from scratch in Python**, including:

- 🔧 Manual forward & backward propagation
- 🧮 Batch Normalization implementation
- 🔥 ReLU activation for hidden layers
- 📊 Softmax activation for output layer (multi-class classification)
- 🎯 Cross-entropy loss for training
- 🛡️ L2 Regularization for improved generalization and weight control

All features are coded without external deep learning frameworks to fully understand the mechanics of training deep networks.

---

## 🧪 Experiment Summary
📝 Note: All experiments were conducted on the MNIST handwritten digits dataset — a widely used benchmark in image classification. The dataset contains 60,000 training images and 10,000 test images of digits (0–9), each of size 28×28 pixels (flattened into a 784-dimensional vector).
Additionally, 20% of the training data (12,000 images) was set aside as a validation set for model evaluation during training.

### ✅ Without BatchNorm (lambda=0)
- **Best Batch Size**: `16`
- **Accuracy**: `0.9212`
- **Runtime**: `37.5s`
- ⚖️ *If runtime is important*: Use batch size `32` with similar accuracy (~0.88) and faster runtime.

### ✅ With BatchNorm (lambda=0)
- **Best Batch Size**: `128`
- **Accuracy**: `0.913`
- **Runtime**: `69.2s`

### ✅ With L2 Regularization (lambda=0.05), No BatchNorm
- **Best Batch Size**: `16`
- **Accuracy**: `~0.94`
- **Runtime**: `113s`

### ✅ With L2 + BatchNorm
- **Best Batch Size**: `64`
- **Accuracy**: `0.915`
- **Runtime**: `112s`

---

## 📉 Insights

- Batch size 16 consistently gave high accuracy, but with a trade-off in runtime.
- Batch normalization shifts the optimal batch size due to added computation.
- L2 regularization had limited effect due to lack of overfitting in the base network.
- Weight differences with/without L2 were minimal.
