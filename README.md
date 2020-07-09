# BYOL
PyTorch implementation of "Bootstrap Your Own Latent: A New Approach to Self-Supervised Learning" by J.B. Grill et al.

**Support for PyTorch <= 1.5.0
**Benchmarks on vision datasets (CIFAR-10 / STL-10).
**Distributed Data Parallel training

Open BYOL in Google Colab Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1B68Ag_oRB0-rbb9AwC20onmknxyYho4B?usp=sharing)


## Installation
```
git clone https://github.com/spijkervet/byol --recurse-submodules -j8
pip3 install -r requirements.txt
python3 main.py
```


## Usage
To run pre-training using BYOL with the default arguments (1 node, 1 GPU), use:
```
python3 main.py
```

Which is equivalent to:
```
python3 main.py --nodes 1 --gpus 1
```

## Multi-GPU / Multi-node training
Use `python3 main.py --gpus 2` to train e.g. on 2 GPU's, and `python3 main.py --gpus 2 --nodes 2` to train with 2 GPU's using 2 nodes.
See https://yangkky.github.io/2019/07/08/distributed-pytorch-tutorial.html for an excellent explanation.

### Arguments
```
--image_size, default=224, "Image size"
--learning_rate, default=3e-4, "Initial learning rate."
--batch_size, default=42, "Batch size for training."
--num_epochs, default=100, "Number of epochs to train for."
--checkpoint_epochs, default=10, "Number of epochs between checkpoints/summaries."
--dataset_dir, default="./datasets", "Directory where dataset is stored.",
--num_workers, default=8, "Number of data loading workers (caution with nodes!)"
--nodes, default=1, "Number of nodes"
--gpus, default=1, "number of gpus per node"
--nr, default=0, "ranking within the nodes"
```
