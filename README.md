# Hypothesis-testing
# Hypothesis Testing: Weekly Operating Costs Analysis

This script performs a hypothesis test to evaluate whether the weekly operating costs are higher than the theoretical model suggests. The test compares the sample mean with the theoretical mean using a one-sample z-test.

## Overview
The goal of this test is to determine whether there is strong evidence to support the claim that the weekly operating costs exceed the theoretical mean. The decision is based on comparing the test statistic with the critical z-value for a specified significance level.

## Methodology
1. **Assumptions**:
   - The data follows a normal distribution.
   - The sample size is 25.
   - The standard deviation of the population is known.

2. **Given Data**:
   - Sample mean: 3050
   - Theoretical mean: 4000
   - Population standard deviation: \( \sigma = 5 \times 25 \)
   - Sample size: \( n = 25 \)
   - Significance level: \( \alpha = 0.05 \)

3. **Steps**:
   - Calculate the standard error.
   - Compute the test statistic (t).
   - Find the critical value (z).
   - Compare the test statistic with the critical value.
   - Draw a conclusion.

## Results
- **Test Statistic (t)**: -38.00
- **Critical Value (Z)**: 1.64
- **Conclusion**: Fail to reject the null hypothesis. There is not enough evidence to support the claim that the weekly operating costs are higher than the model suggests.

## Usage
### Prerequisites
- Python 3.x
- Required libraries:
  - `math`
  - `scipy`
  - `numpy`
  - `matplotlib`

### How to Run
1. Clone this repository:
   ```bash
   git clone <repository-url >
   ```
2. Navigate to the repository:
   ```bash
   cd <repository-name>
   ```
3. Run the script:
   ```bash
   python hypothesis_testing.py
   ```

## Code Explanation
```python
import math
import scipy.stats as stats
import numpy as np
import matplotlib.pyplot as plt

# Given Data
sample_mean = 3050
theoretical_mean = 4000
sigma = 5 * 25
n = 25
alpha = 0.05

# Calculations
standard_error = sigma / math.sqrt(n)
t_statistic = (sample_mean - theoretical_mean) / standard_error
z_critical = stats.norm.ppf(1 - alpha)

# Hypothesis Testing
if t_statistic > z_critical:
    result = "Reject the null hypothesis."
    conclusion = "There is strong evidence to support the claim that the weekly operating costs are higher than the model suggests."
else:
    result = "Fail to reject the null hypothesis."
    conclusion = "There is not enough evidence to support the claim that the weekly operating costs are higher than the model suggests."

# Output Results
print(f"Test Statistic (t): {t_statistic:.2f}")
print(f"Critical Value (Z): {z_critical:.2f}")
print(result)
print(conclusion)
```

## Output
```plaintext
Test Statistic (t): -38.00
Critical Value (Z): 1.64
Fail to reject the null hypothesis.
There is not enough evidence to support the claim that the weekly operating costs are higher than the model suggests.
```

## License
This project is licensed under the MIT License.
