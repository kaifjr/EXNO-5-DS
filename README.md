# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

 from google.colab import drive
drive.mount('/content/drive')

ls drive/MyDrive/'Colab Notebooks'/

import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# **LINE GRAPH**

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

plt.plot(x,y)
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('LINE GRAPH')
plt.legend(['X-Axis and Y-Axis'])

![image](https://github.com/user-attachments/assets/9175bfc2-b046-4f73-b201-da32f55097df)

x1 = [1,2,3]
y1 = [2,4,1]
x2 = [1,2,3]
y2 = [4,1,3]

plt.plot(x1,y1)
plt.plot(x2,y2)
plt.xlabel('X-Axis')
plt.ylabel('Y-Axis')
plt.title('TWO LINE GRAPH')
plt.legend(['Line1','Line2'])

![image](https://github.com/user-attachments/assets/ec904dc7-d139-4bc6-82da-75fee73c8674)

x = [1, 2, 3, 4, 5]
y1 = [10, 12, 14, 16, 18]
y2 = [5, 7, 9, 11, 13]
y3 = [2, 4, 6, 8, 10]
plt.plot(x,y1)
plt.plot(x,y2)
plt.plot(x,y3)
plt.xlabel('X-Axis')
plt.ylabel('Y-Axis')
plt.title('THREE LINE GRAPH')
plt.legend(['Y1-line','Y2-line','Y3-line'])

![image](https://github.com/user-attachments/assets/ff36f6f2-c9c7-4230-87bd-7ef8863cca3b)

x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]
plt.plot(x_values, y_values)
plt.fill_between(x_values, y_values, color='blue', alpha=0.3)
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Graph with Fill Between')
plt.legend(['X&Y Values'])

![image](https://github.com/user-attachments/assets/8df4f074-365c-4b4e-8a70-0e5604d84ab1)

from scipy.interpolate import make_interp_spline
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])
spline = make_interp_spline(x, y, k=3)
x_smooth = np.linspace(x.min(), x.max(), 200)
y_smooth = spline(x_smooth)
plt.plot(x_smooth, y_smooth, color='blue')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Cubic Spline Interpolation')
plt.legend()

![image](https://github.com/user-attachments/assets/7458bb3e-0a63-4d98-b0f4-804712f61b39)

# **BAR GRAPH**

values = [5, 6, 3, 7, 2]
names  = ["A", "B", "C", "D", "E"]
plt.bar(names, values, color='blue', edgecolor='black',alpha=0.5)
plt.xlabel('Categories', fontsize=12)
plt.ylabel('Values', fontsize=12)
plt.title('Bar Graph of Values vs Categories', fontsize=14)
plt.grid(axis='y', linestyle='--', alpha=0.7)

![image](https://github.com/user-attachments/assets/ebabbaa6-7476-4a6c-a490-e6fdddb71ef8)

values = [5, 6]
names = ["A", "B"]
c1 = ['red', 'green']
c2 = ['b', 'g']
plt.bar(names, values, color=c1, edgecolor='black')
plt.xlabel('Categories', fontsize=12)
plt.ylabel('Values', fontsize=12)
plt.title('Bar Chart with Custom Colors (c1)', fontsize=14)

![image](https://github.com/user-attachments/assets/1e013e65-b9a2-4143-95f4-baff6ec6ff31)

plt.bar(names, values, color=c2, edgecolor='black')
plt.xlabel('Categories', fontsize=12)
plt.ylabel('Values', fontsize=12)
plt.title('Bar Chart with Alternate Colors (c2)', fontsize=14)

![image](https://github.com/user-attachments/assets/5d536922-90d1-42d5-bebd-3eb5398c61c6)

df = sns.load_dataset("tips")
avg_total_bill = df.groupby("day")["total_bill"].mean()
avg_tip = df.groupby("day")["tip"].mean()
df

![image](https://github.com/user-attachments/assets/7d29f3cc-7379-49e2-b099-b7f931f315e0)

plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

![image](https://github.com/user-attachments/assets/df1d10ec-79ed-4cae-a926-7e2b07b7ad9f)

# **SCATTER PLOT**

x_values = [0, 1, 2, 3, 4, 5]
y_values = [0, 1, 4, 9, 16, 25]
plt.scatter(x_values, y_values, color='blue', s=100, edgecolor='black')
plt.xlabel('X-axis', fontsize=12)
plt.ylabel('Y-axis', fontsize=12)
plt.title('Scatter Plot of X vs Y', fontsize=14)
plt.grid(True, linestyle='--', alpha=0.7)

![image](https://github.com/user-attachments/assets/8ae9e9ad-a8dd-4727-b21a-d42701c0b6d8)

x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y = [2, 4, 5, 7, 6, 8, 9, 11, 12, 12]
plt.scatter(x, y, label="Stars", color="green", marker="*", s=30)
plt.xlabel("X-axis", fontsize=12)
plt.ylabel("Y-axis", fontsize=12)
plt.title("Scatter Plot with Stars", fontsize=14)
plt.legend(['Stars Plot'])

![image](https://github.com/user-attachments/assets/3ffe894d-cff1-4f81-928b-b3c7a98d86ed)

# **Pie-chart**

activities = ['eat', 'sleep', 'work', 'play']
slices = [3, 7, 8, 6]
colors = ['r', 'y', 'g', 'b']
plt.pie(slices, labels=activities, colors=colors, autopct='%1.1f%%', startangle=90)
plt.title("Activity Distribution")

![image](https://github.com/user-attachments/assets/78e989b2-04ac-4593-b133-0103b0a05443)

# Result:
 Include your result here
