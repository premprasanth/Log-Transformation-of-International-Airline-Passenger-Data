# Ex.-3-Log-Transformation-of-International-Airline-Passenger-Data

## Name: PREM PRASANTH J

## Roll no: 2305001028

## Department: CSE

## AIM

To apply a logarithmic transformation to the International Airline Passenger time series and compare the original and transformed data.

## PROGRAM

### i) Python Code

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

df = pd.read_csv("AirPassengers.csv")

df['Month'] = pd.to_datetime(df['Month'])

df.set_index('Month', inplace=True)

print("Original Data:")
print(df.head())

plt.figure(figsize=(12, 5))
plt.plot(
    df.index,
    df['Passengers'],
    marker='o'
)

plt.title('International Airline Passengers')
plt.xlabel('Year')
plt.ylabel('Passengers (Thousands)')
plt.grid(True)
plt.show()

df['Log_Passengers'] = np.log(df['Passengers'])

print("\nLog Transformed Data:")
print(df.head())

plt.figure(figsize=(12, 5))
plt.plot(
    df.index,
    df['Log_Passengers'],
    marker='o'
)

plt.title('Log-Transformed Airline Passenger Data')
plt.xlabel('Year')
plt.ylabel('Log(Passengers)')

plt.grid(True)
plt.show()

fig, axes = plt.subplots(2, 1, figsize=(12, 8))

axes[0].plot(df.index, df['Passengers'])
axes[0].set_title('Original Airline Passenger Series')
axes[0].set_ylabel('Passengers')
axes[0].grid(True)

axes[1].plot(df.index, df['Log_Passengers'])
axes[1].set_title('Log-Transformed Airline Passenger Series')
axes[1].set_ylabel('Log(Passengers)')
axes[1].set_xlabel('Year')
axes[1].grid(True)

plt.tight_layout()
plt.show()
```

## OUTPUT
<img width="940" height="574" alt="image" src="https://github.com/user-attachments/assets/22045959-8d32-4662-8497-b8b6a6b1a6c1" />


## RESULT

The logarithmic transformation was successfully applied to the International Airline Passenger time series, and the original and transformed data were compared using Python.
