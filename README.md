
# Adversarial Robustness in MNIST Classification

This project investigates the vulnerability of neural networks to adversarial examples using the MNIST dataset. It implements white-box adversarial attacks (FGSM and PGD), visualizes their impact on model performance, and explores adversarial training as a defense strategy.

---

##  Objectives
- Implement FGSM and PGD adversarial attacks.
- Evaluate the robustness of a CNN model on adversarial examples.
- Perform adversarial training using mixed datasets (clean + adversarial).
- Compare pre- and post-defense accuracy across varying epsilon values.
- Visualize model vulnerability and defense effectiveness.

---

## Methodology

### 1. **Model Training**
- A simple CNN was trained on the MNIST dataset to serve as the target model.
- Achieved baseline accuracy: **98.65%**

### 2. **FGSM Attack**
- Fast Gradient Sign Method (FGSM) implemented and applied across the test set.
- Accuracy dropped based on perturbation strength (ε):
  - At ε = 0.1 → Accuracy: **84.36%**
  - At ε = 0.8 → Accuracy: **11.15%**

### 3. **PGD Attack**
- Projected Gradient Descent (PGD) applied for stronger attacks.
- Accuracy dropped drastically:
  - At ε = 0.1 → Accuracy: **83.25%**
  - At ε = 0.3 → Accuracy: **0.06%**

### 4. **Adversarial Training**
- Model retrained using a dataset composed of:
  - 40% clean images
  - 30% FGSM adversarial images
  - 30% PGD adversarial images
- Improved robustness to adversarial attacks (especially FGSM).

---

## Results Summary

| Attack Type | Epsilon | Accuracy (Before Defense) | Accuracy (After Defense) |
| ----------- | ------- | ------------------------- | ------------------------ |
| FGSM        | 0.1     | 84.36%                    | 96.18%                   |
| FGSM        | 0.8     | 11.15%                    | 36.47%                   |
| PGD         | 0.1     | 83.25%                    | 96.24%                   |
| PGD         | 0.3     | 0.06%                     | 87.19%                   |


---

## Project Structure
├── 1.MNIST_Adversarial_target_cnn_trained.ipynb # CNN model training
├── 2.FGSM_attack.ipynb # FGSM attack implementation 
├── 3.PGD.ipynb # PGD attack implementation 
├── 4.Adversarial_Defense_Model_training_On_adversarial_examples_.ipynb # Defense via adversarial training 
├── mnist_cnn.pth # Baseline model weights 
├── mnist_cnn_adversarially_trained.pth # Robust model weights
├── README.md # Project documentation


---

## 🧩 Future Work
- Implement black-box attacks.
- Explore other defenses like:
  - Input preprocessing
  - Label smoothing
  - Ensemble defenses
- Organize results into a single summary notebook for easier sharing and comparison.

---

## 👨‍💻 Author
**Nikhar Asthana**  
This project was built as part of my learning journey into adversarial machine learning and model robustness.  
Looking for AI/ML research internship opportunities to apply and deepen this knowledge.

---

## 📜 License
This project is open for educational and research use.
