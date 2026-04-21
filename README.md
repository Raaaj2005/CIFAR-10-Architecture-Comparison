# CIFAR-10 Architecture Comparison

This repository provides a comparative study of three distinct deep learning architectures—**VGG**, **ResNet**, and **MobileNet**—implemented from scratch using TensorFlow and Keras. The project evaluates these models on the classic CIFAR-10 dataset to benchmark their accuracy, parameter efficiency, and training time.

## 🚀 Project Overview
The goal of this project is to demonstrate the evolution and trade-offs of convolutional neural network (CNN) paradigms:
- **VGG-style**: A classic deep CNN utilizing stacked $3 \times 3$ convolutions and max-pooling.
- **ResNet-style**: Incorporates **Residual Connections** (identity shortcuts) to facilitate the training of deeper networks by mitigating the vanishing gradient problem.
- **MobileNet-style**: Focused on efficiency, using **Depthwise Separable Convolutions** to drastically reduce the number of parameters without a massive loss in performance.

## 🛠️ Architecture Details

### 1. VGG-style CNN
- **Parameters**: ~3.2 Million
- **Key Features**: Stacked convolutional layers with Batch Normalization and Dropout for regularization.

### 2. ResNet-style
- **Parameters**: ~2.8 Million
- **Key Features**: Custom residual blocks with skip connections. Uses Global Average Pooling instead of large dense layers at the end to keep parameters lower than a standard VGG.

### 3. MobileNet-style
- **Parameters**: ~278,000 (Highly Efficient)
- **Key Features**: Replaces standard convolutions with depthwise and pointwise layers. This model has roughly **1/10th** the parameters of the other two models.

## 📊 Performance Benchmarks
Based on training for 30 epochs with **Data Augmentation** (horizontal flips and shifts):

| Model | Accuracy | Training Time | Parameters |
| :--- | :--- | :--- | :--- |
| **VGG** | ~88.1% | ~774s | 3,249,994 |
| **ResNet** | ~89.2% | ~850s | 2,782,154 |
| **MobileNet** | ~85.4% | ~820s | 278,730 |

*Note: While ResNet achieved the highest accuracy, MobileNet demonstrated incredible efficiency, achieving competitive results with a fraction of the computational footprint.*

## 🔧 Installation & Usage
1. **Requirements**:
   - Python 3.12+
   - TensorFlow 2.19+
   - NumPy, Matplotlib

2. **Run the Notebook**:
   Simply open the `.ipynb` file in Google Colab or Kaggle (which supports GPU acceleration) to reproduce the results.

## 📈 Training Strategy
- **Data Augmentation**: Used to prevent overfitting on the small $32 \times 32$ images.
- **Callbacks**: Implemented `ReduceLROnPlateau` and `EarlyStopping` to optimize the learning rate and prevent unnecessary computation.
- **Preprocessing**: Images normalized to [0, 1] and labels converted via One-Hot Encoding.

## ✍️ Author
Name: Raj Fatehveer Singh Brar<br>
Email ID: rbrar_be23@thapar.edu<br>
University: Thapar Institute of Engineering and Technology
