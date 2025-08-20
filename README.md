# Smart Reactor: Machine Learning (V2)

This project explores the application of **Physics-Informed Neural Networks (PINNs)** to model and solve complex chemical kinetics problems, using the **Belousov-Zhabotinsky (BZ) reaction** as a primary case study. The objective is to predict the kinetic behavior of reactions by integrating physical laws directly into the machine learning model.

---

## Project Overview

The goal of this project was to build a model capable of predicting the kinetic behavior of a reaction using experimental data. We started with a basic neural network for regression, then advanced to PINNs to solve systems of differential equations. The final task was to perform an inverse analysis on the BZ reaction to estimate its key parameters.

For a deep dive into the theory and detailed results, please see the **[full project report](ugp-2.pdf)**.

---

## Models Implemented

This repository includes Python scripts for several models, each demonstrating a different concept:

* **ANN Regression:** A simple neural network to model a quadratic equation with noisy data.
* **Forward PINNs:**
    * **Harmonic Oscillator:** Solves the ODEs for `sin(x)` and `cos(x)`.
    * **Damped Harmonic Oscillator:** Models damped oscillatory motion.
    * **BZ Reaction:** Solves the stiff Oregonator model for the BZ reaction.
* **Inverse PINNs:**
    * **Diffusion Equation:** Estimates the unknown diffusion coefficient `C` from solution data.
    * **BZ Reaction:** Infers the key reaction parameters `ε`, `q`, and `f` from synthetic data.

---

## Results: Inverse BZ Reaction

The inverse model successfully estimated the parameters for `ε` and `f` with high accuracy. The parameter `q` proved more challenging due to the system's stiffness but converged with more training.

**Final Parameter Estimates:**
* **ε (epsilon):** 0.040034 (True: 0.040000)
* **f:** 0.670908 (True: 0.666667)
* **q:** 0.002624 (True: 0.000800)

![Parameter Convergence Plot](https://i.imgur.com/zV4Q5fG.png)

---

## How to Run

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/your-username/smart-reactor-ml.git](https://github.com/your-username/smart-reactor-ml.git)
    cd smart-reactor-ml
    ```

2.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run a Script**
    For example, to run the inverse BZ reaction model:
    ```bash
    python inverse_bz_reaction.py
    ```

---

## Repository Files

* `README.md`: This overview file.
* `ugp-2.pdf`: The full, detailed project report.
* `/scripts`: A directory containing all the Python scripts for the models.
* `requirements.txt`: Required Python libraries.
