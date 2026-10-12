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

## Setup

Python 3.10+ is recommended.

```bash
python -m pip install -r requirements.txt
```

Open `CIFAR10_TransferLearning_Comparison.ipynb` in Jupyter Notebook, JupyterLab, or VS Code, then run cells from top to bottom. The first run downloads CIFAR-10 and pretrained ResNet-18 weights, so internet access is required.

## Windows / Anaconda SSL certificate troubleshooting

If pip fails with an SSL certificate verification error:
1. Update certificates and pip in the same environment as the notebook kernel:
   ```bash
   python -m pip install --upgrade pip certifi
   ```
2. If you use Anaconda, update the environment's certificate package using Anaconda Prompt:
   ```bash
   conda update ca-certificates certifi openssl
   ```
3. Restart Jupyter and verify that the notebook kernel uses the intended Python executable.
4. If your network uses a company proxy, use your organization's approved certificate/proxy configuration. Avoid disabling SSL verification.

## Runtime settings

The notebook starts with `QUICK_RUN = True` to validate the workflow faster. It uses small subsets and two epochs. For a fuller experiment, set `QUICK_RUN = False`; this uses the complete training, validation, and test splits and eight epochs by default. Runtime depends on hardware. Consider using a CUDA-enabled GPU.

## Outputs

The notebook creates an `outputs/` folder containing:
- `best_cifar10_resnet18_frozen.pth`
- `best_cifar10_resnet18_fine_tune_layer4.pth`
- `model_comparison.csv`
- `comparison_training_history.csv`
- `experiment_summary.csv`
- `selected_model_*.pth`

Generated data and model checkpoints are not included in the repository because they can be large.

## Important

Do not report an accuracy value in your CV until the notebook has completed and the held-out test metrics have been verified. The quick-run score is not a final benchmark.

## Attribution

This project is adapted and reorganized from the supplied CIFAR-10 image-classification project. Retain the original MIT license and copyright notice when redistributing adapted source material.
