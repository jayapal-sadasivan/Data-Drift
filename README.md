# Data-Drift
In the dynamic world of data science, where models are trained on historical data to predict future outcomes, one constant challenge lurks: data drift. Understanding data drift, its causes, and effective management strategies is crucial for maintaining the performance and reliability of data-driven apps.

Kolmogorov-Smirnov (KS) Test
The KS test is a non-parametric test used to compare the distributions of two datasets. It evaluates the differences between the cumulative distribution functions (CDFs) of the two samples1. Here's how it works:

CDF Comparison: The KS test compares the CDFs of two samples to see how the probabilities of one dataset stack up against another across the entire range of data.

Null Hypothesis: The null hypothesis is that the two samples come from the same distribution.

Test Statistic (D-Statistic): The test provides a D-statistic, which quantifies the maximum difference between the two CDFs.

P-Value: The test also provides a p-value, which indicates the probability of observing the given samples assuming the null hypothesis is true. A low p-value (e.g., less than 0.05) suggests that the samples come from different distributions2.

Feature Drift Analysis
Feature drift refers to changes in the statistical properties of the input features of a model over time. Detecting feature drift is crucial for maintaining model performance, as drift can lead to biased predictions and decreased accuracy3. Here's how feature drift analysis works:

Data Profiling: Summarize the key statistical characteristics of the data, such as distribution, common values, and missing information.

Rolling Window Analysis: Use a rolling window approach to compare the statistical properties of the current data with the historical data.

Drift Detection: Apply statistical tests, such as the KS test, to detect significant changes in the distributions of the features.

Combining KS Test with Feature Drift Analysis
By combining the KS test with feature drift analysis, you can effectively monitor and detect data drift in real-time. Here's a step-by-step approach:

Load Data: Load the historical and current datasets.

Calculate Statistical Properties: Calculate the statistical properties (e.g., mean, standard deviation) of the features in the rolling window.

Apply KS Test: Use the KS test to compare the distributions of the current window with the historical data.

Flag Drift: If the p-value is below a predefined threshold (e.g., 0.05), flag the current window as drifted.

Update Flags: Update the calculated_drift_flag column in your DataFrame to indicate whether each record is drifted or not.
