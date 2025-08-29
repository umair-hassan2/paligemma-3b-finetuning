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

## Final mAP Results

| Metric        | Pretrained | Finetuned | Δ Absolute | Δ % Improvement |
|---------------|------------|-----------|------------|-----------------|
| mAP@[0.50:0.95] | 0.083      | **0.134** | +0.051     | **+61.4%**      |
| AP@0.50       | 0.211      | **0.342** | +0.131     | **+62.1%**      |
| AP@0.75       | 0.050      | **0.082** | +0.032     | **+64.0%**      |
| AP (small)    | 0.048      | **0.084** | +0.036     | **+75.0%**      |
| AP (medium)   | 0.245      | **0.372** | +0.127     | **+51.8%**      |
| AP (large)    | 0.262      | **0.359** | +0.097     | **+37.0%**      |


> **Key takeaway:**
> - The model saw a 61% improvement in mAP@[0.50:0.95], showing finetuning significantly improved overall detection quality across IoU thresholds.
> - Both AP@0.50 (+62%) and AP@0.75 (+64%) improved, meaning the model not only detects more objects but also localizes them more accurately.
> - The largest relative gain is on small objects (+75%), which is critical in many real-world tasks where small targets dominate.
> - Performance across large objects improved but not significantly as compare to other improvements. Suggesting that model already handled large objects quite well, leaving less room for finetuned improvements.

---

### Qualitative Results

Below is a comparison of predictions on the first 5 samples which clearly shows the head to head comparison and improvements in finetuned model's localization abilities.

<img width="1462" height="2490" alt="improved_paligemma_q" src="https://github.com/user-attachments/assets/bceaec50-46b4-48cd-9259-5940179f3268" />

*(Left: Pretrained | Right: Fine-tuned)*

---

## 🏆 Acknowledgements
- [Google PaliGemma](https://huggingface.co/google/paligemma2-3b-pt-224)  
- [Hugging Face Transformers](https://huggingface.co/docs/transformers)  
- Hugging Face Valorant Dataset (custom curated)  

---
