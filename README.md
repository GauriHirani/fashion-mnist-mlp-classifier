# Fashion-MNIST MLP Classifier

A project using a multilayer perceptron (MLP) built in PyTorch to classify greyscale images of clothing and accessories from the Fashion-MNIST dataset. The model takes a 28x28 pixel image as input and predicts which of 10 categories it belongs to.

## Setup

The notebook can be run as is, with no separate data download needed. Fashion-MNIST is downloaded automatically through `torchvision` on the first run.

## Key Findings

**Hyperparameter Tuning:**
Learning rate was tuned across eight values from 0.5 to 0.0001, with 0.0005 giving the highest validation accuracy (85%). Accuracy dropped sharply at higher learning rates, falling to 11% at 0.5, reflecting unstable training from overly large weight updates. The smallest learning rate also performed worse, as the model converged too slowly within 10 epochs.

**Final Model:**
The tuned model achieved 85% accuracy on the test set, with precision, recall and F1-score all close to 0.85.

**Class Performance:**
Classes with distinct shapes, such as Trouser, Sandal, Sneaker, Bag and Ankle boot, were classified with high accuracy. The model struggled most with Shirt, which was often confused with T-shirt/top, Pullover and Coat. These are all visually similar upper-body items, and an MLP flattens each image into a single row of pixels, losing the spatial structure that might help tell them apart.

## Tools

Python, PyTorch, torchvision, scikit-learn, pandas, NumPy, Matplotlib, Seaborn
