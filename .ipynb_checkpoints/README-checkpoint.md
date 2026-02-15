# Rethinking Optimal Transport in Offline Reinforcement Learning

This repository contains the official implementation of the **NeurIPS 2024** paper:  
**Rethinking Optimal Transport in Offline Reinforcement Learning**  
by *Arip Asadulaev, Rostislav Korst, Alexander Korotin, Vage Egiazarian, Andrey Filchenkov, and Evgeny Burnaev.*

The repository provides reproducible JAX code for our novel offline reinforcement learning (RL) algorithm based on **Optimal Transport (OT)**. The method is designed to stitch the best trajectories from offline datasets containing demonstrations from multiple experts, some of which may be sub-optimal. The implementation is tested on continuous control tasks from the **D4RL benchmark suite** and demonstrates superior performance compared to state-of-the-art model-free offline RL methods.

---

## Links

- **[Full Paper](https://arxiv.org/abs/2410.14069)**
- **[NeurIPS 2024 Poster](https://neurips.cc/virtual/2024/poster/94076)**  
- **[OpenReview Discussion](https://openreview.net/forum?id=hKloKv7pR2&noteId=kfWePYgQpH)**  

---

## Repository Structure

The repository is organized as follows:

```
configs/
  antmaze/
  door/
  halfcheetah/
  hammer/
  hopper/
  pen/
  relocate/
  walker2d/
ppl.py
README.md
requirements.txt
```

### Details:

- **`configs/`**: Contains YAML configuration files for different environments in the D4RL benchmark suite.  
  - Each subdirectory corresponds to a specific environment (e.g., `antmaze`, `hopper`, `walker2d`), storing its dataset configuration files.  

- **`ppl.py`**: The main script for training the offline RL algorithm.  

- **`README.md`**: This document, providing an overview and usage instructions for the repository.  

- **`requirements.txt`**: Contains the list of Python dependencies required to run the code.  

---

## Getting Started

### Prerequisites

1. Install **MuJoCo**:  
   Follow the [MuJoCo installation guide](https://github.com/openai/mujoco-py#install-mujoco) to install MuJoCo.

2. Install Python dependencies:  
   ```bash
   pip install pip setuptools -U
   pip install -r requirements.txt
   ```

3. Train the model:  
   Run the `ppl.py` script with the desired configuration. For example:
   ```bash
   python ppl.py --dataset_config_path="configs/antmaze/large_diverse_v2.yaml" --train_seed=0 --cuda="0" --w=12
   ```

---

## Acknowledgements

This repository is built upon the awesome **[CORL framework](https://github.com/tinkoff-ai/CORL)** developed by **Tinkoff AI**. We extend our gratitude for their excellent work, which served as a foundation for implementing our algorithm.  

---

## Citation

If you use this code or find our work helpful, please consider citing our paper:

```bibtex
@inproceedings{asadulaev2024rethinking,
    title={Rethinking Optimal Transport in Offline Reinforcement Learning},
    author={Arip Asadulaev and Rostislav Korst and Alexander Korotin and Vage Egiazarian and Andrey Filchenkov and Evgeny Burnaev},
    booktitle={The Thirty-eighth Annual Conference on Neural Information Processing Systems},
    year={2024},
    url={https://openreview.net/forum?id=hKloKv7pR2}
}
```
