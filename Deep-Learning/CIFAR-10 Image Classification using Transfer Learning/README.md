# CIFAR-10 Transfer Learning Comparison

Compare two ResNet-18 transfer-learning strategies on CIFAR-10:

1. `frozen`: train only the new 10-class classification head.
2. `fine_tune_layer4`: train the new head and the final ResNet block.


## Features
- CIFAR-10 data exploration and stratified train/validation split
- Separate held-out test set
- Resize, ImageNet normalization, and training augmentation
- Validation-loss checkpoint selection
- Test accuracy, macro precision/recall/F1, classification report, and confusion matrix
- Training-time and trainable-parameter comparison
- Saved checkpoints, metrics, and training history
- Custom-image prediction helper

## Before you run
- Use Python 3.10 or newer.
- Install dependencies in the same environment as your Jupyter kernel.
- The first run downloads CIFAR-10 and pretrained ResNet-18 weights, so internet access is required.
- The default `QUICK_RUN=True` is a smoke/learning run, not a final benchmark. Set it to `False` for a more meaningful comparison.
- The code saves the best checkpoint for each strategy and a CSV comparison under `outputs/`.

## Outputs

The notebook creates an `outputs/` folder containing:
- `best_cifar10_resnet18_frozen.pth`
- `best_cifar10_resnet18_fine_tune_layer4.pth`
- `model_comparison.csv`
- `comparison_training_history.csv`
- `experiment_summary.csv`
- `selected_model_*.pth`
