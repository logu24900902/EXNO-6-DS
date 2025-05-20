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
![image](https://github.com/user-attachments/assets/70948553-201f-4f67-9484-6c04275ee121)
```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex", linestyle="solid", legend="auto", palette="Set1")
```
![image](https://github.com/user-attachments/assets/a421d1a5-af2f-4d20-b2f6-48594ccd2046)
```
import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day") ["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
```
![image](https://github.com/user-attachments/assets/90683606-c507-429b-afe0-64903427f7c7)
```
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index, avg_total_bill, label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill, label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/3d3f9d8c-73a2-4bc9-9846-ce2a1b00e930)
```
avg_total_bill=tips.groupby('time') ['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
```
![image](https://github.com/user-attachments/assets/3fc2a0f2-80e1-4bbb-ac3e-9053d754f0ca)
```
p1=plt.bar(avg_total_bill.index,avg_total_bill, label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label="Tip", width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
```
![image](https://github.com/user-attachments/assets/e40ebfc2-2f12-418a-b469-a2d29d605e57)
```
import seaborn as sns
df=sns.load_dataset("tips")
sns.barplot(x="day",y="total_bill", hue="sex", data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
```
![image](https://github.com/user-attachments/assets/2d77ffaf-91b2-4c07-9983-0de66adabbbd)
```
import seaborn as sns
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip", hue="sex", data=df, palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
```
![image](https://github.com/user-attachments/assets/22baa552-fb9f-486f-ac36-413d8a48d2a6)
```
sns.histplot(data=df,x="total_bill", hue="smoker", kde=True, palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")
```
![image](https://github.com/user-attachments/assets/0f7b5f3f-12d7-4aed-bb52-6bfc2f48f43c)
```
import seaborn as sns
import pandas as pd
df=sns.load_dataset('tips')
sns.boxplot(x='day', y='total_bill', hue='sex', data=df, palette='Set2')
```
![image](https://github.com/user-attachments/assets/1b803bb7-5ad7-47df-826a-1703ac7c027b)
```
sns.boxplot (x="day",y="total_bill", hue="smoker",
data=df, linewidth=2,width=0.6,
fliersize=7, flierprops={"marker":"o", "markerfacecolor":"grey"},
boxprops={"facecolor":"red", "edgecolor":"black"},
whiskerprops={"color":"darkblue", "linestyle":"--", "linewidth":2},
capprops={"color":"darkblue","linestyle":"-","linewidth": 2},palette="Set1")
```
![image](https://github.com/user-attachments/assets/bcb0309e-265d-4241-9fc1-31c42f67d640)
```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette='Set1',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/6f696e8f-2d0e-46e2-aea7-70061bc0035d)
```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x = 'day', y = 'tip', data = tip, palette="Set2")
```
![image](https://github.com/user-attachments/assets/e959972b-1e8b-42ae-848c-97facb848be3)
```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"], palette="Set1")
```
![image](https://github.com/user-attachments/assets/e73a14da-933e-48b8-972f-0ee3cf3afdde)
```
import seaborn as sns
sns.set(style="whitegrid")
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip, palette="rainbow")
```

![image](https://github.com/user-attachments/assets/03d4adca-da07-421c-bed8-8cdff2a541c5)
```
sns.kdeplot(data=tips,x='total_bill', hue='time', multiple="layer", linewidth=3, palette='Set2', alpha=0.8)
```

![image](https://github.com/user-attachments/assets/6eecb509-eb4b-47ec-afbb-6ee86f45ba3d)
```
sns.kdeplot(data=tips,x='total_bill', hue='time', multiple='stack', linewidth=3, palette='Set3',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/8716394d-4107-4297-990c-4794a8979f72)
```
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='fill', linewidth=3, palette='Set1', alpha=0.8)
```

![image](https://github.com/user-attachments/assets/2f29a28f-58ca-461a-b98f-e7825539f9ef)
```
import seaborn as sns
tip = sns.load_dataset('tips')
num=tips.select_dtypes (include=['float64', 'int64']).columns
corr=tips[num].corr()
sns.heatmap (corr, annot=True, cmap="YlGnBu")
```
![image](https://github.com/user-attachments/assets/9155198f-9a0a-4f94-b335-09a016dac3b1)
```
sns.heatmap(corr,cmap="YlGnBu")
```
![image](https://github.com/user-attachments/assets/20b678dd-3aa2-4532-aad5-c2d0171d30eb)

# Result:
Thus the data visualization techniques of seaborn has been implemented.

