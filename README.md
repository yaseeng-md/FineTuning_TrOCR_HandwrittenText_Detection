# OCR Using TrOCR on IAM Dataset ✍️📄

This project implements Optical Character Recognition (OCR) for handwritten text using state-of-the-art TrOCR models. The focus is on fine-tuning pretrained models to achieve high accuracy on real-world handwriting datasets.

## 🧠 Problem Statement

Develop an accurate and efficient handwriting recognition system using advanced deep learning models trained on publicly available datasets. The model must be capable of handling diverse handwriting styles, varying noise levels, and irregular layouts.

## 📚 Datasets Used

Three high-quality datasets were used for training and evaluation:

1. **IAM_TrOCR Dataset** (Kaggle)  
   Handwritten line images with corresponding ground-truth labels.  
   ➤ [Kaggle Dataset](https://www.kaggle.com/datasets/changheonkim/iam-trocr)

2. **IAM Handwritten Forms Dataset** (Kaggle)  
   Scanned handwritten forms with printed labels for ground truth extraction.  
   ➤ [Kaggle Dataset](https://www.kaggle.com/datasets/naderabdalghani/iam-handwritten-forms-dataset)

3. **Teklia IAM-Line Dataset** (Hugging Face)  
   Pre-segmented line images from IAM forms, ready for training.  
   ➤ [Hugging Face Dataset](https://huggingface.co/datasets/Teklia/IAM-line)

## 🛠️ Preprocessing Techniques

- **Region extraction** from printed and handwritten zones using pixel slicing.
- **Pytesseract** used to extract printed text as ground truth.
- **CLAHE** (Contrast Limited Adaptive Histogram Equalization) and a custom sharpening filter applied to enhance clarity.
- Image resizing and normalization to fit TrOCR input requirements (384x384).

## 🤖 Models Trained

1. **TrOCR Large Handwritten**  
   🔹 Best performer with CER: `0.459`, WER: `0.586`  
   🔗 [Model](https://huggingface.co/microsoft/trocr-large-handwritten)

2. **TrOCR Base Stage 1**  
   🔹 CER: `0.505`, WER: `0.600`  
   🔗 [Model](https://huggingface.co/models?search=trocr-handwritten-base-stage-1)

3. **Teklia TrOCR Base Stage 1**  
   🔹 Fine-tuned on Teklia IAM-Line  
   🔹 CER: `0.551`, WER: `0.633`  

4. **CLAHE + Sharpen + TrOCR Large**  
   🔹 Despite enhancement, performed lower (CER: `0.731`, WER: `0.930`)

## 📈 Performance Metrics

| Model                                | Dataset Used               | CER     | WER     |
|-------------------------------------|----------------------------|---------|---------|
| TrOCR Large Handwritten             | IAM_TrOCR                  | 0.459   | 0.586   |
| TrOCR Base Stage 1                  | IAM_TrOCR                  | 0.505   | 0.600   |
| Teklia TrOCR Base Stage 1           | Teklia IAM-Line            | 0.551   | 0.633   |
| CLAHE + Sharpen + TrOCR Large       | IAM Handwritten Forms      | 0.731   | 0.930   |

## ⚙️ Platforms Used

- 🧪 Kaggle (Tesla P100 GPU)
- ☁️ Google Colab (T4 GPU)

## 🔧 Hyperparameters

- Epochs: `10`
- Learning Rate: `5e-5`
- Batch Size: `4 or 8` (depending on model type)

## 🚧 Challenges Faced

- Access issues with official IAM and IMGUR5K datasets
- Broken download links and GitHub script failures

## 📂 Notebooks

- [TrOCR Large Handwritten on Kaggle](https://www.kaggle.com/code/yaseeng/trocr-large-handwritten)
- [Teklia IAM-Line Notebook](https://www.kaggle.com/code/yaseeng/teklia-iam-line)
- [Google Colab Notebook 1](https://colab.research.google.com/drive/19zbWtzBtP_JfDy7bGnwKkhW1Ni_7QZ2D?usp=sharing)
- [Google Colab Notebook 2](https://colab.research.google.com/drive/1v6NxQEzG5GNYFA18iAifTtUrG_LXvAxe?usp=sharing)

## 👤 About Me

**Gandluru Mohammed Yaseen**  
M.Tech in Artificial Intelligence & Machine Learning  
Lovely Professional University  
📧 [gandlurumohammedyaseen@gmail.com](mailto:gandlurumohammedyaseen@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/yaseeng-md/)  
💻 [GitHub](http://www.github.com/yaseeng-md)

---

Feel free to ⭐ the repo and explore the notebooks!
