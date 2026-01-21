# Assignment-1 

# Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

---

## Objective
Given the NO2 feature `x`, we transform it into `z` using a roll-number-parameterized non-linear transform and estimate the parameters of the PDF:

$$
\hat{p}(z)=c\*e^{-\lambda(z-\mu)^2}
$$

---

## Dataset
- Dataset: India Air Quality dataset
- Feature used: **NO2** (`no2`)
- Link: https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

---


## Methodology

The complete methodology consists of the following steps:

### **Step-1: Non-Linear Transformation**

Each NO2 value x is transformed into a new variable z using the roll-number-parameterized transformation:

z = x + ar _ sin(br _ x)

where

$$
a_r = 0.05(r \bmod 7), \quad b_r = 0.3((r \bmod 5)+1)
$$

For roll number **102303738**:
- $r \bmod 7 = 6 \Rightarrow a_r = 0.3$
- $r \bmod 5 = 2 \Rightarrow b_r = 0.9$

---

This transformation introduces non-linearity and ensures that the transformed data is unique for each student based on their roll number.

---

### **Step-2: Learning the Probability Density Function**

The transformed variable z is modeled using the following probability density function:

p̂(z) = c _ exp( -λ _ (z - μ)² )

The parameters of the PDF are learned using statistical estimation:

μ (Mean) is estimated as the sample mean of z
σ² (Variance) is computed from the transformed data
λ (Lambda) is calculated as:  
 λ = 1 / (2 \* σ²)
c (Normalization constant) is calculated as:  
 c = sqrt( λ / π )

This ensures that the probability density function integrates to 1.

---

### **Step-3: Parameter Submission**

The learned parameters μ, λ, and c are reported as the final outcome of the assignment.

---

## Results

### Estimated Parameters

The estimated parameters obtained after applying the transformation and learning the PDF are:

| Parameter                  | Value                 |
| -------------------------- | --------------------- |
| μ (Mean)                   | 25.804148934144695    |
| λ (Lambda)                 | 0.0014596395020856768 |
| c (Normalization Constant) | 0.021554992084857203  |

These values are specific to the given roll number and dataset.


---


## Tools & Technologies Used

- Python
- Google Colab
- NumPy
- Pandas

---

## Repository Structure

```
PDF using Non Linear Model
├── Assignment1(PredictiveAnalytics)_102303738.ipynb
└── README.md
```

## Conclusion

In this assignment, a probability density function was learned from real-world NO2 air quality data using a roll-number-parameterized non-linear transformation. The transformed data was modeled using a Gaussian-shaped probability density function, and its parameters were estimated using statistical techniques. The obtained results correctly represent the distribution of the transformed variable. Since the transformation depends on the university roll number, the learned parameters may vary for different students.
