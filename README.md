# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 09/03/2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
# Step 1: Load the dataset,Convert 'Month' column to datetime format,Set it as index
data = pd.read_csv('AirPassengers.csv',parse_dates=['Month'],index_col='Month')
# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['#Passengers'], model='additive',period=12)
# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size for a square shape
# decomposition.plot() this plots all four of teh following graphs
# Original Data
plt.subplot(411)
plt.plot(data['#Passengers'], label='Monthly Passengers')
plt.legend(loc='upper left')
plt.title('Monthly Passengers')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```















### OUTPUT:
<img width="1281" height="374" alt="image" src="https://github.com/user-attachments/assets/a0a6781e-bbb0-4e3c-b9df-2181efa8bdff" />
<img width="1236" height="385" alt="image" src="https://github.com/user-attachments/assets/56081191-bd1d-42b0-abe5-e6002dd5da07" />
<img width="1234" height="377" alt="image" src="https://github.com/user-attachments/assets/6d2f5fc7-872a-419e-9327-fd4288cf0f58" />
<img width="1224" height="373" alt="image" src="https://github.com/user-attachments/assets/d4c5648a-ab7e-47f4-86dd-96f1691e9be6" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
