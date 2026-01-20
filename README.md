# India Air Quality Analysis - NO2 Transformation & Parameter Estimation

## 1. Methodology
This assignment implements a statistical analysis of the Nitrogen Dioxide ($NO_2$) feature from the India Air Quality dataset.

**Step 1: Feature Transformation**
The feature $x$ ($NO_2$) is transformed into a new variable $z$ using a non-linear transformation function specific to the student's University Roll Number ($r$).
$$z = x + a_r \cdot \sin(b_r \cdot x)$$

Where the constants are calculated as:
- $a_r = 0.05 \cdot (r \pmod 7)$
- $b_r = 0.3 \cdot ((r \pmod 5) + 1)$

**Step 2: Parameter Learning**
The transformed data $z$ is modeled using a Probability Density Function (PDF):
$$\hat{p}(z) = c \cdot e^{-\lambda(z-\mu)^2}$$

The parameters are learned using Maximum Likelihood Estimation (MLE):
- **$\mu$ (Mean):** $\frac{1}{N}\sum z_i$
- **$\lambda$ (Precision):** $\frac{1}{2\sigma^2}$
- **$c$ (Constant):** $\frac{1}{\sigma\sqrt{2\pi}}$

## 2. Description
This project is a lab assignment demonstrating data transformation and statistical modeling techniques. 
The Python script reads environmental data, cleans missing values, and applies a trigonometric transformation unique to the user's ID. It then calculates the optimal parameters ($\mu, \lambda, c$) to fit the transformed data to a Gaussian-like distribution.

## 3. Input / Output
**Input:**
- **Source Data:** `data.csv` (India Air Quality Data).
- **Configuration:** University Roll Number (Integer) used as a seed for transformation constants.

**Output:**
- **Console Output:**
  - Calculated constants $a_r$ and $b_r$.
  - Learned PDF parameters: Mean ($\mu$), Lambda ($\lambda$), and Constant ($c$).
- **Data:** A dataframe with the new transformed column $z$.

## 4. Dataset Source
*Since this is a local script-based assignment, there is no deployed live link. The source dataset used is:*
[Kaggle - India Air Quality Data](https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data)

## 5. Output Screenshot
![Console Output]("screenshot.png")
*(Place a screenshot of your Python terminal showing the learned parameters here)*
