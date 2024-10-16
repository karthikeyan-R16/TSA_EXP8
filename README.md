# Ex.No: 08     MOVINTG AVERAGE MODEL AND EXPONENTIAL SMOOTHING
# DEVELOPED BY: Karthikeyan R
# REGISTER NO: 212222240045
### Date: 


### AIM:
To implement Moving Average Model and Exponential smoothing Using Python.
### ALGORITHM:
1. Import necessary libraries
2. Read the electricity time series data from a CSV file,Display the shape and the first 20 rows of
the dataset
3. Set the figure size for plots
4. Suppress warnings
5. Plot the first 50 values of the 'Value' column
6. Perform rolling average transformation with a window size of 5
7. Display the first 10 values of the rolling mean
8. Perform rolling average transformation with a window size of 10
9. Create a new figure for plotting,Plot the original data and fitted value
10. Show the plot
11. Also perform exponential smoothing and plot the graph
### PROGRAM:
# Import necessary libraries
```
import pandas as pd
import matplotlib.pyplot as plt
import warnings
```
# Read the electricity time series data from a CSV file
```
file_path = '/content/rainfall.csv'
data = pd.read_csv(file_path)
```
# Display the shape and the first 20 rows of the dataset
```
print("Shape of the dataset:", data.shape)
print("First 20 rows of the dataset:")
print(data.head(20))
```
# Set the figure size for plots
```
plt.figure(figsize=(10, 6))
```
# Suppress warnings
```
warnings.filterwarnings("ignore")
```

# Plot the first 50 values of the 'total_sales' column
```
plt.plot(data['rainfall'][:50], label='Original Data')  
plt.title('Original Data (First 50 Values)')
plt.xlabel('Index')
plt.ylabel('Rainfall') # Changed ylabel to 'Rainfall'
plt.legend()
plt.show()
```
# Perform rolling average transformation with a window size of 5
```
rolling_mean_5 = data['rainfall'].rolling(window=5).mean()
```
# Display the first 10 values of the rolling mean (window size 5)
```
print("First 10 values of Rolling Mean (Window Size 5):")
print(rolling_mean_5.head(10))
```

# Perform rolling average transformation with a window size of 10
```
rolling_mean_10 = data['total_sales'].rolling(window=10).mean()
```

# Create a new figure for plotting
```
plt.figure(figsize=(10, 6))
```

# Plot the original data and fitted value (rolling mean with window 10)
```
rolling_mean_10 = data['rainfall'].rolling(window=10).mean() 

# Assuming 'rainfall' is the correct column to plot
plt.plot(data['rainfall'], label='Original Data')  
plt.plot(rolling_mean_10, label='Rolling Mean (Window Size 10)', color='red') # Now using the calculated rolling_mean_10
plt.title('Original Data vs Rolling Mean (Window Size 10)')
plt.xlabel('Index')
# Changing ylabel to 'Rainfall' to match the data being plotted
plt.ylabel('Rainfall')  
plt.legend()
plt.show()
```
# Perform Exponential Smoothing
```
exp_smooth = data['total_sales'].ewm(span=10, adjust=False).mean()
```
# Create a new figure for plotting
```
plt.figure(figsize=(10, 6))
```
# Plot the original data and exponential smoothing
```
plt.plot(data['rainfall'], label='Original Data') # Changed 'total_sales' to 'rainfall'
plt.plot(exp_smooth, label='Exponential Smoothing', color='green')
plt.title('Original Data vs Exponential Smoothing')
plt.xlabel('Index')
# Changed ylabel to 'Rainfall' to be consistent with the data being plotted
plt.ylabel('Rainfall')  
plt.legend()
plt.show()
```
### OUTPUT:
# FIRST 50:

![image](https://github.com/user-attachments/assets/d1715b73-7e2a-4f62-b89e-0037bde58c26)


# ROLLING MEAN:

![image](https://github.com/user-attachments/assets/e63b18d6-2182-4d18-8621-ec4666e07b93)


# Exponential Smoothing

![image](https://github.com/user-attachments/assets/3ead708e-e640-4fa4-9ffe-62648214c634)



### RESULT:
Thus we have successfully implemented the Moving Average Model and Exponential smoothing using python.
