# Abigail Ray | Robust Statistics — Automated Anomaly Detection

## Objective
I looked at how different statistics react to extreme values in California housing prices, and used two methods to find outliers in the data.

## Methodology
- Computed six summary statistics (mean, median, trimmed mean, standard deviation, IQR, MAD) on 20,640 California housing observations
- Built Tukey Fences by hand using Q1, Q3, and the IQR to flag price outliers
- Ran an Isolation Forest across all eight features to catch outliers that involve more than one variable at once
- Compared the Tukey and Isolation Forest results and found they flag mostly different rows, since each one is looking for a different kind of unusual observation
- Corrupted 5% of the price data on purpose and recomputed all six statistics to see which ones held up

## Key Findings
- After corrupting 5% of the data, the mean shifted by 67.13%, while the median only shifted by 3.56%
- The statistics built to ignore extreme values (median, trimmed mean, IQR, MAD) barely moved after contamination, while the statistics that use every value directly (mean, standard deviation) moved a lot
- Tukey Fences and Isolation Forest agreed on only a small number of flagged rows, showing that looking at one variable at a time versus looking at all variables together catches different problems in the data
- Not every flagged observation should be removed — some are real, extreme cases worth understanding rather than deleting
