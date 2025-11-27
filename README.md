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
df=sns.load_dataset("tips")
df
```
<img width="512" height="558" alt="image" src="https://github.com/user-attachments/assets/153e1559-2c04-4ff6-93da-78216a7578bd" />

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```
<img width="999" height="630" alt="image" src="https://github.com/user-attachments/assets/7e3477d1-0e8a-462f-83df-78b76ac971c8" />

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
<img width="828" height="840" alt="image" src="https://github.com/user-attachments/assets/35ffd5c6-1b62-452e-8a95-abae810f57d6" />

```
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
<img width="886" height="867" alt="image" src="https://github.com/user-attachments/assets/a6765fd9-82e9-4e63-82ff-716c0713026a" />

```
avg_total_bill=tips.groupby("time")["total_bill"].mean()
avg_tip=tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average total bill and tip by Time of the Day")
plt.legend()
```
<img width="797" height="820" alt="image" src="https://github.com/user-attachments/assets/75df6039-215a-4ebf-a117-3efc82535ec9" />

```
import seaborn as sns 
df=sns.load_dataset("tips") 
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette='Set3') 
plt.xlabel("Day of the week") 
plt.ylabel("Total bill") 
plt.title("total bill by day and gender")
```
<img width="763" height="775" alt="image" src="https://github.com/user-attachments/assets/858d3b6a-216a-4451-9eac-7751e3483aeb" />

```
import seaborn as sns
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette='Set1')
plt.xlabel("Total bill")
plt.ylabel("Tip")
plt.title("Scatter plot of total bill vs tip amount")
```
<img width="725" height="755" alt="image" src="https://github.com/user-attachments/assets/fd4bf061-9804-4837-ae30-1375a213f3f3" />

```
sns.histplot(x="total_bill",hue="smoker",data=df,kde=True,palette='Set1')
plt.xlabel("Total bill")
plt.ylabel("Frequency")
plt.title("Distribution of total bill by gender")
```
<img width="811" height="733" alt="image" src="https://github.com/user-attachments/assets/e8c607cf-5ead-45c1-9960-e4b2cb15142b" />

```
import seaborn as sns
import pandas as pd
df=sns.load_dataset('tips')
sns.boxplot(x='day',y='total_bill',hue="sex",data=df,palette='Set2')
```
<img width="839" height="700" alt="image" src="https://github.com/user-attachments/assets/5120771f-8349-416f-a579-0fcbfc14cf56" />

```
sns.boxplot(x='day',y='total_bill',hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},boxprops={"facecolor":"red","edgecolor":"black"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":"-","linewidth":"2"},palette='Set1')
```
<img width="1237" height="668" alt="image" src="https://github.com/user-attachments/assets/5a47813f-afb8-4806-a0a4-b977df6a3032" />

```
sns.violinplot(x='day',y='total_bill',hue="smoker",data=tips,linewidth=2,width=0.6,palette='Set1',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total bill")
plt.title("Violin plot of total bill by day and smoker status")
```
<img width="1133" height="722" alt="image" src="https://github.com/user-attachments/assets/35c09bcd-363c-4af9-9f9f-90de0ed3bfff" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip,palette='Set2')
```
<img width="727" height="701" alt="image" src="https://github.com/user-attachments/assets/c0afe540-0046-4070-8119-55240df8d489" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"],palette='Set1')
```
<img width="665" height="705" alt="image" src="https://github.com/user-attachments/assets/2443bc1c-9ee9-4f60-98d9-f4cce4798c63" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip,palette='rainbow')
```
<img width="746" height="691" alt="image" src="https://github.com/user-attachments/assets/4cf5bca9-ae7d-451c-bc0e-a727e781ce42" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="layer",linewidth=3,palette='Set2',alpha=0.8)
```
<img width="1048" height="650" alt="image" src="https://github.com/user-attachments/assets/c2dce702-f2f1-4a4b-8cd5-36095cccdd36" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="stack",linewidth=3,palette='Set3',alpha=0.8)
```
<img width="1067" height="631" alt="image" src="https://github.com/user-attachments/assets/4beccc01-9fe7-4bb7-a0d5-971cb96209d3" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="fill",linewidth=3,palette='Set1',alpha=0.8)
```
<img width="1008" height="662" alt="image" src="https://github.com/user-attachments/assets/568d552b-161b-406c-b22e-88f775d8ddc9" />

```
import seaborn as sns
tip=sns.load_dataset('tips')
num=tips.select_dtypes(include=['float64','int64']).columns
corr=tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```

```
sns.heatmap(corr,cmap="YlGnBu")
```
<img width="668" height="618" alt="image" src="https://github.com/user-attachments/assets/4adae50e-095c-4e65-88b9-d3fafe39332e" />

# Result:
 Result is successfully executed
