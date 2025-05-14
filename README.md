# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

```
NAME: V. POOJAA SREE
REG.: 212223040147

```

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

TO CAPTURE A TREND

# 1. Line Chart

```
import matplotlib.pyplot as plt
import numpy as np
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.plot(x,y)
plt.show()

```

# Output:

![1](https://github.com/user-attachments/assets/5f60ce96-852a-4103-8b27-d1c6efc14cac)


# 2.Multi-Line Chart

```
x1=[1,2,3]
y1=[2,4,1]
plt.plot(x1,y1,label="line 1")
x2=[1,2,3]
y2=[4,1,3]
plt.plot(x2,y2,label="line 2")
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Multi-Line Chart')
plt.legend()
plt.show()

```

# Output:

![2](https://github.com/user-attachments/assets/fff9c62d-02b8-4e6a-a15e-ac3d635e6bda)


# 3.Area Chart

```
x=[1,2,3,4,5]
y1=[10,12,14,16,18]
y2=[5,7,9,11,13]
y3=[2,4,6,8,10]
plt.fill_between(x,y1,color='blue')
plt.fill_between(x,y2,color='green')
plt.plot(x,y1,color='red')
plt.plot(x,y2,color='black')
plt.legend(['y1','y2'])
plt.show()

```

# Output:

![3](https://github.com/user-attachments/assets/8bdc43b1-68c9-4363-8c7b-80b53d745aee)


# 4.Stacked Area Chart

```
plt.stackplot(x,y1,y2,y3,labels=['Line 1','Line 2','Line 3'])
plt.legend(loc='upper left')
plt.title('Stacked Line Chart')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()

```

# Output:

![4](https://github.com/user-attachments/assets/7db84090-9875-4082-8cac-b93887afedaa)


# 5.Spline Chart

```
from scipy.interpolate import make_interp_spline
x=np.array([1,2,3,4,5,6,7,8,9,10])
y=np.array([2,4,5,7,8,8,9,10,11,12])
spl=make_interp_spline(x,y)
x1=np.linspace(x.min(),x.max(),100)
y1=spl(x1)
plt.plot(x,y,'*',label='data')
plt.plot(x1,y1,'-',label="spline")
plt.legend()
plt.show()

```

# Output:

![5](https://github.com/user-attachments/assets/240c8c10-6f35-48cc-a9e9-268c03f5dd14)



TO VISUALIZE RELATIONSHIPS

# 1.Bar Chart

```
val=[5,6,3,7,2]
names=["A","B","C","D","E"]
plt.bar(names,val,color="blue")
plt.show()

```

# Output:

![6](https://github.com/user-attachments/assets/7ad0a17f-7e11-458a-9503-1bfcfae02d63)


# 2.Scatter Plot

```
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.scatter(x,y,s=30,color="red")
plt.show()

```

# Output:

![7](https://github.com/user-attachments/assets/50f009d0-3a7b-4786-8938-515715e46cfb)


# 3.Bubble Chart

```
x = [1, 2, 3, 4, 5]
y = [10, 15, 20, 25, 30]
sizes = [100, 200, 300, 400, 500]
plt.scatter(x, y, s=sizes, alpha=0.5)
plt.xlabel('x_values')
plt.ylabel('y_values')
plt.title('Bubble Chart')
plt.show()

```

# Output:

![8](https://github.com/user-attachments/assets/575ca9d8-3f41-46b4-8b0e-f341f7d629c5)



TO CAPTURE DISTRIBUTIONS

# 1.Histogram

```
ages=[2,5,70,40,30,45,50,45,43,40,44,60,7,13,57,18,90,77,32,21,20,40]
range=(0,100)
bins=10
plt.hist(ages,bins,range,color='purple',histtype='bar',rwidth=0.8)
plt.xlabel('age')
plt.ylabel('No. Of People')
plt.title('Histogram')
plt.show()

```

# Output:

![9](https://github.com/user-attachments/assets/0d0315d0-38bf-4879-be7f-49bb3bca5862)


# 2.Box Plot

```
np.random.seed(0)
data=np.random.normal(loc=0,scale=1,size=100)
data
fig,ax=plt.subplots()
ax.boxplot(data)
ax.set_xlabel('Data')
ax.set_ylabel('Values')
ax.set_title('Box Plot')

```

# Output:

![10](https://github.com/user-attachments/assets/49fc06e6-cee8-464f-a132-fb3a3554ee79)


# 3.Violin Plot

```
data = [np.random.normal(loc=0, scale=1, size=100),
        np.random.normal(loc=2, scale=1, size=100),
        np.random.normal(loc=1, scale=2, size=100)]
plt.violinplot(data)
plt.xlabel('Groups')
plt.ylabel('Values')
plt.title('Violin Plot')
plt.xticks([1, 2, 3], ['Group 1', 'Group 2', 'Group 3'])
plt.show()

```

# Output:

![11](https://github.com/user-attachments/assets/90193ee2-3990-47f3-86b6-b762df84b462)


# 4.Density Chart

```
data = np.random.normal(0, 1, 1000)
plt.hist(data, bins=30, density=True, alpha=0.5)
plt.title('Density Plot Example')
plt.xlabel('Values')
plt.ylabel('Density')
from scipy.stats import gaussian_kde
kde = gaussian_kde(data)
x_vals = np.linspace(min(data), max(data), 1000)
plt.plot(x_vals, kde(x_vals), 'r')
plt.show()

```

# Output:

![12](https://github.com/user-attachments/assets/73fc488d-dbc3-48f0-8d40-8a0381a9f04a)


# 5.Pie Chart

```
act=['eat','sleep','work','play']
slices=[3,7,8,6]
color=['r','y','g','b']
plt.pie(slices,labels=act,colors=color,startangle=90,shadow=True,explode=(0.1,0.1,0.1,0.1),radius=1.2,
autopct='%1.1f%%')
plt.legend()
plt.show()

```

# Output:

![13](https://github.com/user-attachments/assets/dd580647-3c8a-4087-8b74-e795ee7d1d46)



# Result:

```
Thus, the data visualization techniques using matplotlib has been executed successfully.

```
