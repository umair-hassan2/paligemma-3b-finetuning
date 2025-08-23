# 🎯 Valorant Object Detection with Google PaliGemma  

This project explores **fine-tuning Google’s PaliGemma model** for **object detection in Valorant gameplay**, showcasing my ability to work with **vision-language models, quantization, and low-resource fine-tuning techniques**.
Model weights are publically available on hugging face and can be downloaded from [here](https://huggingface.co/umairhassan02/paligemma2_finetuned).

---

## 🚀 Project Overview  
- Used **Hugging Face datasets** for Valorant objects.  
- Compared **pretrained vs. fine-tuned performance** on the detection task.  
- Applied **QLoRA (4-bit quantization)** for memory efficiency while retaining model performance.  
- Inference pipeline built with **Hugging Face Processor + Model APIs**.  

---

## ⚡ Key Techniques  
- **Pretraining baseline evaluation** → measured performance on dataset without adaptation.  
- **Fine-tuning with QLoRA** → adapted the model to Valorant domain.  
- **Quantization (4-bit)** → saved GPU memory while enabling efficient fine-tuning.  
- **Evaluation metrics** → IoU (per class), mAP, Accuracy, Recall.  

---

## 📊 Results  

### Quantitative Improvements

| Metric            | Pretrained | Fine-tuned | % Improvement |
|-------------------|------------|------------|---------------|
| Avg IoU (Class 0) | 0.0017     | 0.0046     | **+171%**     |
| Avg IoU (Class 1) | 0.0070     | 0.0570     | **+714%**     |
| Avg IoU (Class 2) | 0.0140     | 0.0850     | **+507%**     |
| Avg IoU (Class 3) | 0.0210     | 0.0970     | **+362%**     |
| mAP               | 0.0000     | 0.0070     | –             |
| Accuracy          | 1.0000     | 0.9960     | -0.4%         |
| Recall            | 1.0000     | 0.9960     | -0.4%         |

> **Key takeaway:** Fine-tuning significantly boosts IoU across all classes (up to **7× improvement**) while maintaining nearly perfect accuracy and recall.

---

### Qualitative Results

Below is a comparison of predictions on the first 5 samples:

<img width="1462" height="2490" alt="valorant-pred-comparison" src="https://github.com/user-attachments/assets/cdb7ce90-357a-43f0-a31f-89384764f365" />

*(Left: Pretrained | Right: Fine-tuned)*

---

## 📊 Training Dynamics

### Per-Class IoU Progression
Below we visualize **how IoU improves per class during training**, comparing pretrained vs fine-tuned.

| Pretrained | Fine-tuned |
|------------|------------|
| <img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_04_17 AM" src="https://github.com/user-attachments/assets/16d90f45-26ea-42a4-b9ce-bae4fcad6894" /> | <img width="2528" height="1328" alt="finetuned-teammate" src="https://github.com/user-attachments/assets/65249b0e-6e70-4749-a6e8-0ffbef2bd790" /> |
| <img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_05_02 AM" src="https://github.com/user-attachments/assets/1895d4c9-3734-4835-a5bc-dea102f98167" /> |<img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_09_53 AM" src="https://github.com/user-attachments/assets/324b6edd-1bb2-47e8-a065-a1c28ad5180e" />|
| <img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_05_22 AM" src="https://github.com/user-attachments/assets/d764e681-a168-42f2-9c9d-c408eeeba08f" /> | <img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_10_06 AM" src="https://github.com/user-attachments/assets/7b52d5a0-4f11-4a58-b1d2-c03b4aaf38a7" />|
| <img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_07_10 AM" src="https://github.com/user-attachments/assets/6ea6b788-79f2-4fa0-8f5c-7503e5495d67" />|<img width="2528" height="1328" alt="W B Chart 8_24_2025, 2_09_53 AM" src="https://github.com/user-attachments/assets/324b6edd-1bb2-47e8-a065-a1c28ad5180e" />|
---

## 🏆 Acknowledgements
- [Google PaliGemma](https://huggingface.co/google/paligemma2-3b-pt-224)  
- [Hugging Face Transformers](https://huggingface.co/docs/transformers)  
- Hugging Face Valorant Dataset (custom curated)  

---
