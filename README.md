# 👗 Fashion MNIST Image Generation using GAN (PyTorch)

This project implements a **Generative Adversarial Network (GAN)** from scratch in PyTorch to generate fashion item images similar to those in the **Fashion MNIST** dataset. The GAN learns to generate 28x28 grayscale images of clothing items such as shirts, pants, sneakers, and coats over 150 training epochs.

---

## 🧠 Project Overview

| Component         | Description                                  |
|------------------|----------------------------------------------|
| Dataset          | Fashion MNIST (downloaded via `torchvision`) |
| Framework        | PyTorch                                       |
| Model Type       | Vanilla GAN (1 Discriminator + 1 Generator)  |
| Image Size       | 28x28 grayscale                              |
| Latent Space     | 64-dimensional noise vector                  |
| Epochs           | 150                                           |
| Batch Size       | 100                                           |
| Optimizer        | Adam                                          |
| Loss Function    | Binary Cross Entropy (BCE)                   |
| Output           | 150+ sample images at various training stages |

---

## 📦 Dataset

The project uses the [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset, downloaded automatically via PyTorch’s `torchvision.datasets.FashionMNIST`:
No manual download required.

---

## 🧩 Model Architectures

### 🔹 Generator

```text
Input: 64-dim noise vector
→ Linear → ReLU
→ Linear → ReLU
→ Linear → Tanh
Output: 784-dim image vector (reshaped to 28x28)
```

### 🔹 Discriminator

```text
Input: 784-dim image vector
→ Linear → LeakyReLU
→ Linear → LeakyReLU
→ Linear → Sigmoid
Output: Probability of real vs fake
```

---

## 🔁 Training Details

* **Device:** Runs on CPU or GPU automatically
* **Learning Rate:** 0.0002
* **Epochs:** 150
* **Checkpoint:** Generator images saved every epoch in `/samples/`
---

## 📈 Results & Observations

| Metric                 | Description                                    |
| ---------------------- | ---------------------------------------------- |
| **Losses Tracked**     | Discriminator Loss, Generator Loss             |
| **Training Stability** | Stable across 150 epochs with BCE loss         |
| **Visual Quality**     | Improves significantly after 50+ epochs        |
| **Best Epochs**        | \~100–150 (images resemble shoes, pants, etc.) |

---

## 🧠 Key Learnings

* Learned how **discriminators and generators** compete during adversarial training
* Understood the **importance of loss balancing**
* Visualized how noise vectors evolve into **structured fashion items**
* Observed **mode collapse** and mitigated by tuning learning rates

---
