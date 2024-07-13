For the practical implementation of the mean comparison for two populations, the Heart Disease dataset from Kaggle was used (Source: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset).  

<img width="292" alt="daten (1)" src="https://github.com/user-attachments/assets/30f99669-87b5-4c18-865c-6ebd7646d6dd">

The dataset contains medical and demographic information from 1025 anonymized patients. Researchers and data analysts use it to identify patterns and correlations that can help diagnose heart disease. Our study focused specifically on the serum cholesterol column.

1. Data preparation

First, the cholesterol column of the dataset was checked for missing values (NaN) and anomalous outliers. None were found and the data types were suitable for further analysis. Therefore, no changes were made to the dataset. Instead, it was divided into two groups: Patients diagnosed with heart disease (526) and healthy patients (499).


2. Definition of the hypotheses and the significance level

The significance level (α) is set at 0.05, which means that the probability of a difference being considered significant is 5%. This setting is a common practice in statistical analyses to determine whether differences between populations are significant.
For the calculation of the conclusion, the method of p-values and not the one of confidence intervals has been used.

If H0 can be rejected, this means that the null hypothesis is rejected. With a significance level of α = 0.05, this is done with a confidence level of 95%. This means that the results are statistically significant and are not based on chance, but that there is actually a real pattern or relationship in the data set. 
Null hypothesis (H₀):
It is assumed that the mean cholesterol level is the same in diagnosed and undiagnosed individuals:

H₀ = "The mean cholesterol level is the same in diagnosed and undiagnosed individuals".

Alternative hypothesis (H₁):
It is assumed that the mean cholesterol level is higher in diagnosed individuals than in undiagnosed individuals:

H₁ = "The average cholesterol level is higher in diagnosed individuals than in undiagnosed individuals".

3. Calculations
a) Mean value and standard deviation:

Means and standard deviations were calculated for both populations (diagnosed and undiagnosed individuals). 
![Screenshot 2024-06-30 184639](https://github.com/user-attachments/assets/36f74972-9704-4c32-be5c-8247c1bbc73b)

The mean indicates the average value of the variable under consideration within each group, while the standard deviation measures the dispersion of these values around the mean.

b) T-Score calculation: 

The T-score was calculated using the patient counts, means and standard deviations of the two groups. The numerator (referred to as 'numerator' in the code) is the difference between the mean of the cholesterol values in diagnosed patients ('chol_mean_diagnosed_patients') and the mean in healthy patients ('chol_mean_healthy_patients').

The denominator is the square root of the sum of the variance-weighted standard deviations of the two populations.

![Screenshot 2024-06-30 185059](https://github.com/user-attachments/assets/6b174f25-5a4c-4b85-a7b4-435942017ef0)


The T-score is compared with the significance level and this makes it possible to determine whether the differences between the groups are significant and do not occur by chance.


c) Calculation of the p-value:

The p-value is calculated using the cumulative distribution function (CDF) of the t-distribution. This is a specialized distribution function for the T-test:
![Screenshot 2024-06-23 195834](https://github.com/user-attachments/assets/92203879-909f-4f66-824e-85d4b7e20eb9)

The p-value indicates the probability of obtaining a T-score or greater for a given level of significance (here α = 0.05) if the null hypothesis (H0) were true. A small p-value indicates that the data show significant differences between the groups.

4. Interpretation of the results

Since the calculated p-value ( 0.9993368838319615) is greater than the significance level, the null hypothesis (H₀) cannot be rejected. This means that the mean cholesterol level is not significantly different in diagnosed and undiagnosed individuals.

In conclusion, one could say that cholesterol alone is not sufficient to accurately diagnose heart disease. Given the data set, the assumption that people with higher cholesterol levels are more likely to suffer from heart disease cannot be confirmed.

