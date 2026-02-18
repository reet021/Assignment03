# Learn Probability Density Function using Roll-Number-Parameterized Non-Linear Model

## Project Overview

This project learns the parameters of a Gaussian-type Probability Density Function (PDF) using a roll-number-based non-linear transformation applied to NO₂ air quality data.

Dataset used: India Air Quality Data (Kaggle)  
Feature used: NO₂ concentration

---

## Dataset

Source: Kaggle – India Air Quality Data  
Feature: NO2

The dataset contains air pollution measurements across Indian cities.

---

## Step 1: Non-Linear Transformation

Each NO₂ value (x) is transformed into (z) using:

z = x + ar * sin(br * x)

Where:

ar = 0.05 × (r mod 7)  
br = 0.3 × ((r mod 5) + 1)

- r = University Roll Number  
- mod = remainder operator  

This introduces controlled non-linearity based on the roll number.

---

## Step 2: Learning the Probability Density Function

The learned model:

p̂(z) = c * exp(-λ (z - μ)²)

This represents a Gaussian distribution.

Parameters:

- μ (mu): Mean (center of distribution)
- λ (lambda): Controls spread
- c: Normalization constant

---

## Parameter Estimation Method

Parameters were estimated using:

- Histogram-based density estimation
- Non-linear curve fitting using scipy.optimize.curve_fit

---

## Results

Estimated Parameters:

λ  = 0.002057486697464275  
μ  = 19.62960741231495  
c  = 0.02680223003602028  

The fitted PDF closely matches the empirical distribution of the transformed variable.

---

## How to Run

Install required libraries:

pip install numpy pandas matplotlib scipy

Run the Python script or notebook to:
1. Load dataset
2. Apply roll-number-based transformation
3. Estimate parameters
4. Plot learned probability density function

---

## Output

- Transformed data visualization
- Learned Probability Density Function plot
- Estimated parameters (λ, μ, c)

---

## Learning Outcomes

- Understanding non-linear transformations
- Probability density estimation
- Gaussian distribution modeling
- Parameter estimation using curve fitting
