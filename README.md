# Roll‑Number Driven PDF Learning (Advanced Mathematics)

## Project Description

This assignment builds a **roll‑dependent nonlinear statistical model** to approximate a Probability Density Function (PDF) from real environmental observations. The dataset consists of Nitrogen Dioxide (NO₂) air‑pollution readings which are first distorted using a custom transformation derived from the student roll number and then modeled using a Gaussian‑type function.

For this submission, the roll number used is:

**r = 102303048**

---

## Dataset Information

* Source: https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data
* Required File: `data.csv`
* Column Used: `no2`

---

## Mathematical Formulation

1. Data Transformation
The feature 
x
 (NO2) is transformed into 
z
 using the following non-linear equation:

z
=
x
+
a
r
sin
⁡
(
b
r
x
)

Where 
a
r
 and 
b
r
 are derived from the University Roll Number (
r
):

a
r
=
0.05
×
(
r
mod
7
)
b
r
=
0.3
×
(
(
r
mod
5
)
+
1
)
2. Probability Density Function (PDF)
We fit the transformed data to the target function:

p
^
(
z
)
=
c
⋅
e
−
λ
(
z
−
μ
)
2

The parameters are estimated using statistical moments (Mean and Variance):

μ
: Mean of the transformed data 
z
.
λ
: Derived from variance (
λ
=
1
2
σ
2
).
c
: Normalization constant (
c
=
1
2
π
σ
2
).
Prerequisites
---

### Density Model

The transformed observations are fitted to a Gaussian‑shaped density:

p̂(z) = c · exp(−λ(z − μ)²)

Parameters are computed using statistical moments:

* μ : mean of z
* λ : 1 / (2σ²)
* c : 1 / √(2πσ²)

---

## Requirements

Install dependencies before running:

```bash
pip install pandas numpy matplotlib
```

---

## How to Run

1. Place `data.csv` in the project directory.
2. Ensure the roll number inside the notebook/script is:

```python
r = 102303048
```

3. Execute the notebook:

```
PDF_Fitting.ipynb
```

---

## Output

The program prints the learned values:

* λ (lambda)
* μ (mu)
* c (normalization constant)

and generates a histogram with the estimated probability density curve.

---

## Result Visualization
<img width="565" height="413" alt="bb81fc2b-61b6-4a8f-ba39-5e89ae775290" src="https://github.com/user-attachments/assets/49e5834d-0f3a-47f9-8503-875d82957ac6" />

The red curve represents the predicted PDF while the histogram shows the transformed NO₂ data distribution.
