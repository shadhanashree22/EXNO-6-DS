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
![download](https://github.com/user-attachments/assets/205f6706-2e0d-4a05-805d-5a77c9e351ba)

```
df = sns.load_dataset("tips")
df
```
```
total_bill	tip	sex	smoker	day	time	size
0	16.99	1.01	Female	No	Sun	Dinner	2
1	10.34	1.66	Male	No	Sun	Dinner	3
2	21.01	3.50	Male	No	Sun	Dinner	3
3	23.68	3.31	Male	No	Sun	Dinner	2
4	24.59	3.61	Female	No	Sun	Dinner	4
...	...	...	...	...	...	...	...
239	29.03	5.92	Male	No	Sat	Dinner	3
240	27.18	2.00	Female	Yes	Sat	Dinner	2
241	22.67	2.00	Male	Yes	Sat	Dinner	2
242	17.82	1.75	Male	No	Sat	Dinner	2
243	18.78	3.00	Female	No	Thur	Dinner	2
244 rows × 7 columns
```
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![download](https://github.com/user-attachments/assets/16930d48-aa83-4d9c-a1b0-f9a906051945)


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
![download](https://github.com/user-attachments/assets/e291be41-99d0-4957-81e9-42a2326601bd)

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
![download](https://github.com/user-attachments/assets/dc293902-7b99-4a17-8ac0-cc13176d39cd)


```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![download](https://github.com/user-attachments/assets/c2d7576c-d548-4b25-8c5b-91a7cc4fa8b7)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![download](https://github.com/user-attachments/assets/0938a5c4-d048-4f0f-b665-99b6ccbafeb2)

```
tit=pd.read_csv("/content/titanic_dataset (1).csv")
tit
```
```
PassengerId	Survived	Pclass	Name	Sex	Age	SibSp	Parch	Ticket	Fare	Cabin	Embarked
0	1	0	3	Braund, Mr. Owen Harris	male	22.0	1	0	A/5 21171	7.2500	NaN	S
1	2	1	1	Cumings, Mrs. John Bradley (Florence Briggs Th...	female	38.0	1	0	PC 17599	71.2833	C85	C
2	3	1	3	Heikkinen, Miss. Laina	female	26.0	0	0	STON/O2. 3101282	7.9250	NaN	S
3	4	1	1	Futrelle, Mrs. Jacques Heath (Lily May Peel)	female	35.0	1	0	113803	53.1000	C123	S
4	5	0	3	Allen, Mr. William Henry	male	35.0	0	0	373450	8.0500	NaN	S
...	...	...	...	...	...	...	...	...	...	...	...	...
886	887	0	2	Montvila, Rev. Juozas	male	27.0	0	0	211536	13.0000	NaN	S
887	888	1	1	Graham, Miss. Margaret Edith	female	19.0	0	0	112053	30.0000	B42	S
888	889	0	3	Johnston, Miss. Catherine Helen "Carrie"	female	NaN	1	2	W./C. 6607	23.4500	NaN	S
889	890	1	1	Behr, Mr. Karl Howell	male	26.0	0	0	111369	30.0000	C148	C
890	891	0	3	Dooley, Mr. Patrick	male	32.0	0	0	370376	7.7500	NaN	Q
891 rows × 12 columns
```

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![download](https://github.com/user-attachments/assets/87f2e874-0e9f-4639-a51b-e913cf3c3526)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![download](https://github.com/user-attachments/assets/592537f7-378a-42c5-a064-f262179d35a0)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![download](https://github.com/user-attachments/assets/c6a18b30-4979-4894-a58b-5f021d7ce467)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
```
Numerical variable
0	-0.079767
1	-0.440358
2	-0.677613
3	-0.696588
4	0.278365
...	...
995	0.717581
996	-0.317862
997	-0.711180
998	-0.659612
999	-0.382400
1000 rows × 1 columns


dtype: float64
```

```
sns.histplot(data = num_var, kde = True)
```
![download](https://github.com/user-attachments/assets/e5f34e44-d133-4506-8080-18b5b5c3c300)

```
df=pd.read_csv("/content/titanic_dataset (1).csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![download](https://github.com/user-attachments/assets/d8a3400b-44b5-4a88-aeb8-490d0dd15a03)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![download](https://github.com/user-attachments/assets/9fa73016-070a-4f2e-aedb-d0c0789a6622)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![download](https://github.com/user-attachments/assets/9eb71962-f1ed-44f7-94c2-d802fcd64e6b)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![download](https://github.com/user-attachments/assets/8bed4b3b-379b-4612-8590-d36071d909e3)

```
mart=pd.read_csv("/content/titanic_dataset (1).csv")
mart
```
```
PassengerId	Survived	Pclass	Name	Sex	Age	SibSp	Parch	Ticket	Fare	Cabin	Embarked
0	1	0	3	Braund, Mr. Owen Harris	male	22.0	1	0	A/5 21171	7.2500	NaN	S
1	2	1	1	Cumings, Mrs. John Bradley (Florence Briggs Th...	female	38.0	1	0	PC 17599	71.2833	C85	C
2	3	1	3	Heikkinen, Miss. Laina	female	26.0	0	0	STON/O2. 3101282	7.9250	NaN	S
3	4	1	1	Futrelle, Mrs. Jacques Heath (Lily May Peel)	female	35.0	1	0	113803	53.1000	C123	S
4	5	0	3	Allen, Mr. William Henry	male	35.0	0	0	373450	8.0500	NaN	S
...	...	...	...	...	...	...	...	...	...	...	...	...
886	887	0	2	Montvila, Rev. Juozas	male	27.0	0	0	211536	13.0000	NaN	S
887	888	1	1	Graham, Miss. Margaret Edith	female	19.0	0	0	112053	30.0000	B42	S
888	889	0	3	Johnston, Miss. Catherine Helen "Carrie"	female	NaN	1	2	W./C. 6607	23.4500	NaN	S
889	890	1	1	Behr, Mr. Karl Howell	male	26.0	0	0	111369	30.0000	C148	C
890	891	0	3	Dooley, Mr. Patrick	male	32.0	0	0	370376	7.7500	NaN	Q
891 rows × 12 columns
```

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
```
PassengerId	Survived	Age	Name	Ticket	Embarked
0	1	0	22.0	Braund, Mr. Owen Harris	A/5 21171	S
1	2	1	38.0	Cumings, Mrs. John Bradley (Florence Briggs Th...	PC 17599	C
2	3	1	26.0	Heikkinen, Miss. Laina	STON/O2. 3101282	S
3	4	1	35.0	Futrelle, Mrs. Jacques Heath (Lily May Peel)	113803	S
4	5	0	35.0	Allen, Mr. William Henry	373450	S
5	6	0	NaN	Moran, Mr. James	330877	Q
6	7	0	54.0	McCarthy, Mr. Timothy J	17463	S
7	8	0	2.0	Palsson, Master. Gosta Leonard	349909	S
8	9	1	27.0	Johnson, Mrs. Oscar W (Elisabeth Vilhelmina Berg)	347742	S
9	10	1	14.0	Nasser, Mrs. Nicholas (Adele Achem)	237736	C
```
```
sns.kdeplot(data=mart,x='PassengerId')
```
![download](https://github.com/user-attachments/assets/e2a41a30-4a53-47ac-94bb-e7b101b1df2b)

```
sns.kdeplot(data=mart,x='Age')
```
![download](https://github.com/user-attachments/assets/cf7cb6ea-d1d2-4e45-9169-8de6e2b26e9e)

```
sns.kdeplot(data=mart)
```
![download](https://github.com/user-attachments/assets/712f1601-22d3-494d-ac9f-ed449be9921b)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![download](https://github.com/user-attachments/assets/77a65723-d3bc-4174-83eb-48c072074445)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![download](https://github.com/user-attachments/assets/9294344e-a183-4fee-a3ed-d2d578d9cf21)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![download](https://github.com/user-attachments/assets/50cc5865-f351-444b-9dac-14b2fd06f6bb)

```
hm=sns.heatmap(data=data)
```
![download](https://github.com/user-attachments/assets/a05efdc6-0ca8-47e1-829c-38512f8bc522)

# Result:
Thus to Perform Data Visualization using seaborn python library is successfully executed
