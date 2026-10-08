# Confidence Interval Estimation for Industrial Quality Control

Statistical estimation of print-head durability under destructive testing conditions using Python[cite: 3, 4]. This repository demonstrates how to construct confidence intervals for population means under two foundational statistical scenarios: when population variance is unknown (Student's $t$-distribution) versus when population variance is known (Standard Normal $Z$-distribution)[cite: 3, 4].

---

## 📌 Problem Scenario & Context

In manufacturing quality control, destructive testing ensures physical items meet reliability thresholds by operating them until failure[cite: 4]. Because each tested unit is destroyed, sample sizes are constrained by cost[cite: 4].

A manufacturer randomly samples $n = 15$ print-heads to estimate mean lifespan (measured in millions of printed characters)[cite: 3, 4]:
```text
[1.13, 1.55, 1.43, 0.92, 1.25, 1.36, 1.32, 0.85, 1.07, 1.48, 1.20, 1.33, 1.18, 1.22, 1.29]
```[cite: 3, 4]

The objective is to compute and compare **99% Confidence Intervals** under two core settings[cite: 3, 4]:
1. **Unknown Population Standard Deviation ($\sigma$)**: Using sample standard deviation $s$ and the Student's $t$-distribution ($df = n - 1$)[cite: 3, 4].
2. **Known Population Standard Deviation ($\sigma = 0.2$)**: Using the Standard Normal ($Z$) distribution[cite: 3, 4].

---

## 📊 Statistical Formulations

### Case 1: Unknown $\sigma$ (Student's $t$-distribution)
When sample size is small ($n < 30$) and the true population standard deviation $\sigma$ is unknown, the sampling distribution of the sample mean follows Student's $t$-distribution with $df = n - 1$ degrees of freedom[cite: 3, 4]:

$$\bar{x} \pm t_{\alpha/2, \, df} \times \left(\frac{s}{\sqrt{n}}\right)$$

* Sample Mean ($\bar{x}$): `1.2387` million characters
* Sample Std Dev ($s$): `0.1932`
* Degrees of Freedom ($df$): `14`
* Critical Value ($t_{0.005, 14}$): `2.9768`
* **99% Confidence Interval**: **[1.0902, 1.3871]** million characters

### Case 2: Known $\sigma$ ($Z$-distribution)
When the population standard deviation is historically known ($\sigma = 0.20$), the standard normal distribution applies[cite: 3, 4]:

$$\bar{x} \pm z_{\alpha/2} \times \left(\frac{\sigma}{\sqrt{n}}\right)$$

* Population Std Dev ($\sigma$): `0.2000`[cite: 3, 4]
* Critical Value ($z_{0.005}$): `2.5758`[cite: 3]
* **99% Confidence Interval**: **[1.1057, 1.3717]** million characters[cite: 3]

---

## 📁 Repository Structure

```text
├── confidence_intervals.ipynb     # Jupyter Notebook containing statistical calculations
├── requirements.txt               # Required Python packages
└── README.md                      # Project documentation and analysis summary
