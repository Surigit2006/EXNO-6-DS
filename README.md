# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 ```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/207f5a5e-f47c-4483-ac8d-ed757e8af161)
```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/c85175ff-c36d-4055-80f9-c777c3af7195)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/b41191a3-cbc6-47f2-a3de-1b31b9d4fa72)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/7e51e8d5-2bb7-4bb1-a2c3-848a503519cb)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/d71ff0c0-668e-4f0d-9edb-03a741892bc2)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/7758d268-7135-4d59-ac83-e53e1f855f06)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/0086430b-d027-4199-afd1-a7b73e120f2f)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/438af455-ecbd-471a-aa12-3cc95b3f6076)
```
tit=pd.read_csv(r"C:\Users\Suriya\Downloads\titanic_dataset.csv")
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/3c864084-fdf7-4a1d-b30b-fd40558cb009)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/adcf5c0d-9345-4e46-b4c7-cffdcab98988)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/2b0657ed-e03a-4f87-b299-370e3de14af3)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/9e6c034f-1cec-4c7d-ac42-b1c208bf3308)
```
df=pd.read_csv(r"C:\Users\Suriya\Downloads\titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/3fbef74a-84ed-4691-aeca-ee7d46eee7eb)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/2fdd6cc0-dcdc-4197-b610-45b051ae9ead)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/331dddb0-2967-4c9f-981b-5c9127d680bc)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/a362270b-44de-4f21-bbf6-c1b7930e155d)
```
mart=pd.read_csv(r"C:\Users\Suriya\Downloads\titanic_dataset.csv")
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/76e9bcd5-d0a6-4a49-8c6a-6aacce9041e8)
```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/ee3e05e2-c954-4f65-9d26-b1ed72a7d3be)
```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/df758d2f-33eb-4469-80c5-64f13d03a998)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/dd7873cf-619c-430a-b811-bb167c53c0b5)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/6cac9740-357f-4fb6-b25d-bdf8f4d83013)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/546f0458-7158-4f02-abb3-3265d5f09000)
```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/defb7835-1d68-4787-91fb-723778fc621b)








# Result:
 Code executed successfully.
