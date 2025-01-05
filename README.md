# Diabetic-Retina-Detection-Transfer-Learning

## Overview
This project is part of my deep learning course at the university of Oulu, where I explore how **transfer learning** can help detect diabetic retinopathy from retinal images. Diabetic retinopathy is when diabetes leads to blindness, so the goal of this project is to create a model using pretrained ImageNet models and detect DR from patients retina images.

I have experimented with several techniques like fine-tuning pretrained models(Resnet, Densenet, VGG), adding attention mechanisms, ensemble learning (stacking, boosting, bagging, voting, etc), and even visualizing the model’s decision-making process with **Grad-CAM**. The primary metric in this project is **Cohen's Kappa** score.

---

## Steps in Project

1. **Fine-tuning Pretrained Models**  
   In task A, I worked with popular models like ResNet18 and DenseNet121, fine-tuning their parameters and adapting them to the DeepDRiD dataset.

2. **Two-stage Training**  
   For task B, I first trained the models on a larger dataset (APTOS 2019) and then fine-tuned them on a smaller, more specific dataset (DeepDRiD).

3. **Attention Mechanisms**  
   In task C, I tried adding spatial, channel, and self-attention to make the models focus on important regions of the images.

4. **Ensemble Learning**  
   In task D, I corporated ensemble learning approaches and combined predictions from multiple models using methods like stacking, boosting, bagging, soft voting, and weighted averaging to improve accuracy.

5. **Explainable AI**  
   In Task E, by using Grad-CAM, I visualized which parts of the retinal images were most important regions for the model’s predictions and decisions. Warmer colors (like red) show the regions that affect on model's predictions the most.

6. **Preprocessing Techniques**  
   Ultimately, preprocessing techniques like CLAHE, circular cropping, and Gaussian blur were used to highlight important image features.

---

## Datasets

### 1. **DeepDRiD Dataset**
   - A dataset with 2,000 retinal fundus images (4 per patient) with 5 diabetic retinopathy levels: No DR (0), Mild (1), Moderate (2), Severe (3), and Proliferative DR (4).
   - **transformations**: Resized images to 256x256 and applied data augmentations like rotations, flips, crops, colorjitter and transformations like CLAHE.   

### 2. **APTOS 2019 Blindness Detection Dataset**
   - A larger dataset with 3,662 images labeled similarly to DeepDRiD.
   - **transformations**: Pre-trained models on this dataset to improve performance on DeepDRiD.
   - [link to dataset](https://www.kaggle.com/datasets/mariaherrerot/aptos2019)
---

## Results

### Key Metric: **Cohen’s Kappa Score**
- Best dual model (task A): Resnet18 (Cohen’s Kappa = 0.8346).
- Best single model (task B): DenseNet121 (Cohen’s Kappa = 0.8738), using pretrained weights of DeppDRiD-resized.
- Best ensemble: Weighted average method (Cohen’s Kappa = 0.8712).

### Takeaways:
- **Two-stage training** significantly boosted performance compared to direct fine-tuning.
- Attention mechanisms didn’t improve results much—likely due to the small dataset size (or maybe even mistakes in implementations :( ).
- Preprocessing techniques like **CLAHE with circular cropping** helped models focus on critical regions, improving predictions.

---

## Usage

you can simply clone the repository and open it on google Colab or jupyter notebook!

---

If you have any questions or suggestions, feel free to contact me! :)

