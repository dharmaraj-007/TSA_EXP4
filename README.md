DEVELOPED BY: Dharmaraj S

REGISTER NO:212222240025

# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES



### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('tsla_2014_2023 (1).csv', nrows =200)

# Use the 'Close' price column
model = data['high'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)

```
OUTPUT:
SIMULATED ARMA(1,1) PROCESS:
![exp 4 1](https://github.com/user-attachments/assets/da5602ec-3209-487a-b97d-e2cbe6b39c1e)



Partial Autocorrelation
![ex 4 2](https://github.com/user-attachments/assets/a0666d1f-a1ad-43b4-8a83-51cf2bd60cbc)


Autocorrelation

![ex 4 3](https://github.com/user-attachments/assets/2f1768c9-dc41-44fc-b58c-124d5cfea654)


SIMULATED ARMA(2,2) PROCESS:

![ex 4 4](https://github.com/user-attachments/assets/d1f7059f-ce86-4600-bc24-6c33acadf3ef)

Partial Autocorrelation
![Screenshot 2025-04-22 091512](https://github.com/user-attachments/assets/f36ff53f-bff1-4315-a3a0-fa958a66ae77)



Autocorrelation
![Screenshot 2025-04-22 091522](https://github.com/user-attachments/assets/3af2a757-6a1e-400c-aa75-364f1a38f2fd)


## RESULT:
Thus, a python program is created to fir ARMA Model successfully.
