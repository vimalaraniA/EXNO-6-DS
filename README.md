# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY
### NAME : A Vimala Rani
### REGISTER NUMBER : 21223040240
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
<img width="338" alt="ds1" src="https://github.com/user-attachments/assets/24aee5ca-d134-422c-ad1f-39d931422e09" />

```
df = sns.load_dataset("tips")
df
```
<img width="327" alt="ds2" src="https://github.com/user-attachments/assets/d7ec6695-355d-4ebe-bf54-98489a70218f" />
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
<img width="365" alt="ds3" src="https://github.com/user-attachments/assets/fd77bef4-4be6-44c4-b1f2-1a62bce68121" />

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
![ds4](https://github.com/user-attachments/assets/7423bce7-39c6-4e4a-9b8d-4bb67912bf0e)

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

![ds5](https://github.com/user-attachments/assets/d9960925-802b-480c-8da8-ab9072027176)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![ds6](https://github.com/user-attachments/assets/6f69a451-fe47-4450-a8bc-0c1b92e100c0)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![ds7](https://github.com/user-attachments/assets/82e7b62d-f232-4123-89a3-1f8396df818b)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![ds8](https://github.com/user-attachments/assets/46be58c2-8f37-4855-bf9e-c98c76304718)

```
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![ds9](https://github.com/user-attachments/assets/2d5ea1f7-eccb-474a-a6e4-7a3afd35e54a)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
![ds10](https://github.com/user-attachments/assets/dce7440a-c896-4581-9b12-15a311adb2ad)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![ds11](https://github.com/user-attachments/assets/947ac412-2ed2-4ca6-a03e-c8233bab249f)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![ds12](https://github.com/user-attachments/assets/77bcdcad-2374-489e-95fe-12cffbea1bc0)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![ds13](https://github.com/user-attachments/assets/7d7ffa42-a9fe-4549-b04e-96a0ad6ec0b0)

```
sns.histplot(data = num_var, kde = True)
```
![ds14](https://github.com/user-attachments/assets/a44ebf1a-e6bc-47c1-bec2-676da7b766ee)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![ds15](https://github.com/user-attachments/assets/e526f645-59c6-4aaf-b151-104df8746069)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![ds16](https://github.com/user-attachments/assets/bf875880-3671-4b10-baf9-0c9bd96211e2)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![ds17](https://github.com/user-attachments/assets/581c9514-2d14-4e49-ad64-00cfcd92a654)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![ds18](https://github.com/user-attachments/assets/d3154047-be01-44c8-8143-f0cab6abdc12)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![ds19](https://github.com/user-attachments/assets/1e6012a1-b327-4e83-ba4a-82645e388247)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![ds20](https://github.com/user-attachments/assets/0b45e966-6e6a-406a-858d-423773cb635d)

```
sns.kdeplot(data=mart,x='PassengerId')
```
![ds21](https://github.com/user-attachments/assets/b06ba80f-125c-4156-afab-7cfd37cccc08)

```
sns.kdeplot(data=mart,x='Age')
```
![ds22](https://github.com/user-attachments/assets/9991e55e-8aa3-4e5b-8a69-39c602bd335d)

```
sns.kdeplot(data=mart)
```
![ds23](https://github.com/user-attachments/assets/525d0b93-3db6-4128-8837-5670af9cb00f)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![ds24](https://github.com/user-attachments/assets/04d23f0d-1e6c-4b98-a950-4d73986a18e6)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![ds25](https://github.com/user-attachments/assets/b9bfbabd-eb3f-4032-bd69-d962de79a0b2)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![ds26](https://github.com/user-attachments/assets/7f1e98b1-b15a-4a95-b95f-7436d99b915b)

```
hm=sns.heatmap(data=data)
```
![ds27](https://github.com/user-attachments/assets/57b35164-ac75-4a3b-9dbe-c500624e393c)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.


