# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.
```
Developed By Mohanish.K
Ref No: 212222100028
```
# CODE
```
#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()
```
```python3
#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt
```
```python3

#1.Line Plot

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')
```
```python3

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
```
```python3

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)
```
```python3

#4.Violin Plot

sns.violinplot(x="Profit",data=df)
```
```python3

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
```
```python3

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
```python3
#7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
```
```python3
#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
```python3
#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib
```
```python3
#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()
```
```python3
#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
```python3
#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
```
```python3
#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
```
```python3
#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()
```
```python3
#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 
```
```python3
#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUPUT
## Reading the given dataset
<img width="595" alt="171088128-126c7176-a343-4f0d-9775-be64ef025be9" src="https://user-images.githubusercontent.com/93992063/171088625-75b69a10-f573-44f7-9645-c3ce4ef77e5b.png">


## Data Visualization Using Seaborn:
### 1.Line Plot
<img width="336" alt="171088148-00745931-00a9-4e77-9652-bde07ec58041" src="https://user-images.githubusercontent.com/93992063/171088655-27e3a090-4760-4e29-b954-7759a445a8c1.png">
<img width="314" alt="171088166-0622ed0d-983e-4fbb-9a07-ffde6ae73fbf" src="https://user-images.githubusercontent.com/93992063/171088668-5a814d59-6d67-4053-9d35-dc8d6221027a.png">

<img width="258" alt="171088179-9468b1ae-1975-4ddd-8c7d-15a62cde1105" src="https://user-images.githubusercontent.com/93992063/171088679-cdf26bb7-62f0-4ef9-8308-171a7a7a68ef.png">

### 2.Scatterplot
<img width="293" alt="171088199-43c1ab2b-8c36-4787-a25b-9fb447afb27a" src="https://user-images.githubusercontent.com/93992063/171088729-4528fb87-105b-4ad8-8c01-a090178862a6.png">
<img width="284" alt="171088208-7f3a8cdd-e757-4d86-8366-8e7795a10be1" src="https://user-images.githubusercontent.com/93992063/171088737-abadff73-b2cb-4891-9485-5df3bec60db0.png">

<img width="408" alt="171088221-0b5ce909-ea1b-4d11-b544-02a182ae71f8" src="https://user-images.githubusercontent.com/93992063/171088756-decdfb1a-0835-43e8-8fe8-3cdfcd89ed47.png">

### 3.Boxplot
<img width="252" alt="171088266-a16dba86-8fc1-4f39-a43e-8946245952ed" src="https://user-images.githubusercontent.com/93992063/171088805-74233b62-90e2-4af6-af2f-239e5b10d5d1.png">
<img width="283" alt="171088275-5fc74eac-6c9c-4751-9a25-a6bb396b51b0" src="https://user-images.githubusercontent.com/93992063/171088821-f94c7dc4-aa1d-43c1-ab84-8d84af736efb.png">

### 4.Violin Plot
<img width="229" alt="171088288-b57cfa86-14ca-4da3-be85-2aedda3ef070" src="https://user-images.githubusercontent.com/93992063/171088926-239ae44b-4649-42ce-b52e-a6b26cc217f3.png">

### 5.Barplot
<img width="362" alt="171088300-2f65fe18-2157-4408-93b9-621db48d3fe5" src="https://user-images.githubusercontent.com/93992063/171088936-2cefc282-8343-445d-9545-8ba91f5c69d9.png">
<img width="248" alt="171088309-f8fc728a-98de-46da-af45-5504501865a5" src="https://user-images.githubusercontent.com/93992063/171088941-cc06dd62-0713-4963-8470-b91fcfe03c57.png">

### 6.Pointplot
<img width="258" alt="171088319-54fd42f2-c10d-4696-ab1d-cf26b67876ab" src="https://user-images.githubusercontent.com/93992063/171089031-2815c863-58f8-49a0-a276-c82d18e013d5.png">

### 7.Count plot
<img width="267" alt="171088340-ac5e9f66-7ecd-4fbc-b58f-0e8a9c854f58" src="https://user-images.githubusercontent.com/93992063/171089112-95028c42-efbb-48bc-a4f9-99bc774e506e.png">
<img width="258" alt="171088373-3b644c23-eb34-4c62-9854-7beedc247c8e" src="https://user-images.githubusercontent.com/93992063/171089127-9b367b72-de86-4fb3-9ce4-4954afb16e90.png">

### 8.Histogram
<img width="281" alt="171088392-27dc5b70-ca70-4069-ac16-50edbcb51fb0" src="https://user-images.githubusercontent.com/93992063/171089170-f1167adb-d80c-4f26-853d-2795c0befc55.png">

### 9.KDE Plot
<img width="252" alt="171088402-28a45721-eef1-44ae-8a71-8f1cdfc84371" src="https://user-images.githubusercontent.com/93992063/171089192-8ca525cc-0e90-4de8-b04a-de24abdce895.png">

## Data Visualization Using Matplotlib:
### 1.Plot
<img width="268" alt="171088777-b33aa92c-b4f2-4b2e-af45-c86899df03c9" src="https://user-images.githubusercontent.com/93992063/171089267-f747476e-4896-4f55-a2e1-63a31415293b.png">

### 2.Heatmap
<img width="381" alt="171088793-a39c19c3-f481-4837-a9ab-c59bbbb80b72" src="https://user-images.githubusercontent.com/93992063/171089457-c8c4fc0a-1262-41f2-8d31-ffa71daa0ae6.png">

### 3.Piechart
<img width="168" alt="171088813-8407fd7d-2c62-41f5-9e0d-25242f9576ac" src="https://user-images.githubusercontent.com/93992063/171089653-0b9254e6-69e7-43bc-be30-7c787edf8216.png">
<img width="288" alt="171088875-f1b23ed9-0c39-4061-aeeb-bd21c3943308" src="https://user-images.githubusercontent.com/93992063/171089725-6e50a256-7e7a-4162-a533-91fc1c913fc4.png">

### 4.Histogram
<img width="245" alt="171088893-37660289-6bfa-4274-94b9-f9c10373a8a4" src="https://user-images.githubusercontent.com/93992063/171089939-70d1d2b6-24a8-4fd2-aa4e-c1bfb516f403.png">

### 5.Bargraph
<img width="279" alt="171088899-506a8bfe-128b-44a6-aea9-6ad9d68d27e7" src="https://user-images.githubusercontent.com/93992063/171089907-bb79c79f-62b9-4539-a754-1205aab99ac7.png">

### 6.Scatterplot
<img width="248" alt="171088911-4bc14fcd-490e-40bc-a732-d8e733ca4713" src="https://user-images.githubusercontent.com/93992063/171089883-9d4ba8c0-d896-44e0-847c-c4ddb466c61c.png">

### 7.Boxplot

<img width="261" alt="171088927-6bb49da4-25fe-4f10-8dab-11a1f0b68c88" src="https://user-images.githubusercontent.com/93992063/171089859-b1c8d695-4e4b-426e-9718-c84bdc1d75de.png">

# RESULT
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
