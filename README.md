# 🏛️ Egypt-Vision: AI-Powered Landmark Recognition
**Course Project: AI424 - Deep Learning** **Academic Year:** 2025/2026  
**Institution:** Faculty of Artificial Intelligence  

---

## 🌟 Overview
**Egypt-Vision** is a comprehensive end-to-end training pipeline designed to classify iconic Egyptian landmarks. This project demonstrates the practical application of **Deep Learning** and **Computer Vision** to tourism and cultural heritage, using a lightweight architecture optimized for real-world efficiency.

---

## 📝 Compliance with Task Requirements
**Requirement:** > *"Write your own code to modify any pre-trained CNN models and make the suitable fine-tuning to fit your case study."*

**Achievement & Implementation:**
* **Custom Model Architecture:** I selected **MobileNetV2** as the base model for its efficiency. I modified the architecture by removing the top classification layers (`include_top=False`) and integrating a custom head consisting of:
    * `GlobalAveragePooling2D`: To reduce spatial dimensions.
    * `Dropout (0.3)`: To prevent overfitting during the fine-tuning stage.
    * `Dense (Softmax)`: Tailored specifically to classify the selected Egyptian landmarks.
* **Advanced Fine-Tuning Strategy:** I implemented a **Triple-Stage training process** rather than a standard one-step fit:
    1.  **Stage 1 (Feature Extraction):** Training only the custom head while keeping the base frozen.
    2.  **Stage 2 (Partial Fine-Tuning):** Unfreezing the top 30 layers for architectural feature adaptation.
    3.  **Stage 3 (Full Unfreeze):** Unfreezing the entire network with a microscopic learning rate ($5 \times 10^{-6}$) to achieve maximum precision without destroying pre-trained weights.

---

## 🚀 Technical Highlights
* **Base Model:** MobileNetV2 (Pre-trained on ImageNet).
* **Optimization:** Adam Optimizer with Progressive Learning Rate Decay.
* **Regularization:** Early Stopping (Restoring best weights) and Real-time Data Augmentation.
* **Performance:** Achieved **70% Validation Accuracy** on the top 10 most documented landmarks.



---

## 📁 Dataset & Case Study
The project focuses on the **Top 10 most documented Egyptian landmarks** to ensure model reliability and handle the complexity of ancient stone textures:
* *Elephantine, Siwa, Temple of Kom Ombo, Karnak, Muizz Street, Colossi of Memnon, Alexandria Opera House, Montaza Palace, Saint Catherine's Monastery, Na'ama Bay.*

---

## 📈 Results & Evaluation
* **Final Accuracy:** 70.00%
* **Robustness:** The model was tested against unseen images with various rotations, brightness levels, and zoom factors.
* **Weight Integrity:** Used `restore_best_weights` to ensure the final model is the most accurate version saved during training, avoiding the effects of late-epoch fluctuations.



---

## 🛠️ How to Run
1.  Clone the repository.
2.  Open the `notebook.ipynb` in Kaggle or Google Colab.
3.  Ensure the Egypt Landmarks dataset path is correctly pointed.
4.  Run all cells to see the training phases and final evaluation.

---

## 📂 Project Structure
* `notebook.ipynb`: Full Python implementation.
