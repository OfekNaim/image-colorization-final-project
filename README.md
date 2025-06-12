# 🎨 Image Colorization with CNN and GAN

## 📚 Project Overview

This project explores the task of **image colorization**, which involves converting grayscale images into realistic color versions using deep learning. Two methods were implemented and compared:

- **Method A:** Convolutional Autoencoder
- **Method B:** Pix2Pix-based Generative Adversarial Network (GAN) with U-Net

Developed as the final project for the **Advanced Topics in Deep Learning** course, Colman, 2025.

---

## 🧪 Method A – CNN Autoencoder

We implemented a **convolutional autoencoder** for grayscale-to-color image translation.

### ✅ Architecture A
- **Structure:** Encoder-Decoder with Conv2D, Dropout, UpSampling
- **Early stopping** and **Dropout** used to avoid overfitting
- **Activation:** LeakyReLU
- **Loss:** Mean Squared Error (MSE)
- **Optimizer:** Adam
- **Batch Size:** 16

**Result:**  
Training stopped early after just 12 epochs. The model showed early signs of colorization but lacked realism and depth.

---

### ✅ Architecture B
- Removed **early stopping** and **dropout**
- Replaced **UpSampling** with **Conv2DTranspose**
- Trained for 300 epochs

**Result:**  
Significantly improved results with better learning and image realism.

---

## 🧪 Method B – GAN with Pix2Pix (U-Net)

Implemented a **Pix2Pix GAN model** for image colorization.

### 🧠 Generator (U-Net):
- Encoder: 7 Conv2D layers with stride 2
- Decoder: Conv2DTranspose for upsampling
- Skip connections
- Activation: LeakyReLU → tanh

### 🧪 Discriminator:
- Conv2D layers
- Activation: LeakyReLU → Sigmoid
- Loss: **Binary Cross-Entropy + L1 Loss**

**Result:**
- After 10–20 epochs, the GAN showed promising results.
- **Discriminator loss decreased**, while **generator loss remained high**, indicating more training is needed.
- Generated images improved progressively across epochs.

---

## 📁 Project Files

| File Name                                 | Description                        |
|------------------------------------------|------------------------------------|
| `FinalProject.ipynb` | Method A - Training Autoencoder    |
| `InferenceNotebook.ipynb` | Method A - Inference         |
| `Notebook_Method_B.ipynb` | Method B - GAN Training     |
| `InferenceNotebook_Method_B.ipynb` | Method B - GAN Inference  |
| `Final_Project_report.pdf`  | Full project report (PDF)          |

---

## 🚀 How to Use

> Open any inference notebook and follow the steps:

1. **Open with Google Colab**
2. Click: `Runtime → Run All`
3. Upload a **grayscale image** when prompted
4. Click `Submit` – the model will generate a colorized image

---

## 🔗 Colab Links

| Description        | Link |
|--------------------|------|
| Method A - Train   | [Colab Notebook](https://colab.research.google.com/drive/1pBoKfUHvnakcTsBc1S4ohoaP7qw-H0Bi?usp=sharing) |
| Method A - Inference | [Colab Notebook](https://colab.research.google.com/drive/1cXRaU1VWygZHL1JDDJqj9uQJjXSGpubI?usp=sharing) |
| Method B - Train   | [Colab Notebook](https://colab.research.google.com/drive/13hRTMtELGMrRXVA9oMuqfzlyMUuL7LX?usp=sharing) |
| Method B - Inference | [Colab Notebook](https://colab.research.google.com/drive/1TbQcC234Qqc-cmDCsrplPDzhO-qXzDCS?usp=sharing) |

---

## 👥 Authors

- **Ofek Naim** 
- **Hinoy Solomon** 

> Final project submission – Colman 2025
