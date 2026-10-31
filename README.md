# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 31.10.2026
# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity/temperature.
# DATASET: 
HDFC bank stock price data.
# SOFTWARE REQUIRED/TOOL USED: 
Google Colab
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
from matplotlib import pyplot as plt
import pandas as pd
df = pd.read_csv("/content/drive/MyDrive/Time Series/HDFCBANK.NS.csv")
df['Date'] = pd.to_datetime(df['Date'], dayfirst=True, errors='coerce')
df['Close'] = pd.to_numeric(df['Close'], errors='coerce')
df = df.dropna(subset=['Date', 'Close'])
df.set_index('Date', inplace=True)
df_resampled = df['Close'].resample('D').interpolate()
df_resampled.plot(kind='line', label='Closing Price', color='black')
plt.title('Time Series Plot of HDFC Bank Closing Price')
plt.xlabel('Date')
plt.ylabel('Closing Price')
plt.legend()
plt.grid(True)
plt.show()

```

# OUTPUT:
<img width="780" height="516" alt="image" src="https://github.com/user-attachments/assets/9845deef-667f-4876-aff8-f34f2e4887e5" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
