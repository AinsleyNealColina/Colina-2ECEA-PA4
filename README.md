# Colina-2ECEA-PA4(EXPERIMENT 4 DATA WRANGLING AND DATA VISUALIZATION )

## Objectives
1.To identify the codes and functions needed in cleaning and visualizing data

2.To be able to apply and use the different codes and functions in creating a Python program that will 
be used in data wrangling and data visualization.


So we are tasked to:
## Problem 1:Data Frames
1a.Display the data [Name,Gender,Track,Math]. With the condition of Hometown is Visayas and Math less than 70, and name it Vis.

1b.Dispaly the data [Name,GEAS,Electronics].With the condition of Track is instrumentation,Hometown is Luzon, Electronics greater than 70,and name it Instru.

1c.Display the data [Name,Track,Electronics,Average].With the condition of hometown is Mindanao, gender is female, and average >=55,and name it Mindy.

## Problem 2:Visualization
2.Create a visualization that shows how the different features contributes to average grade. Does 
chosen track in college, gender, or hometown contributes to a higher average score? 

Steps:
## Solution 1:Data Frames
1.Before we start we must import pandas as pd and load the excel file.

```python
#To be able to read the excel file
import pandas as pd

# Reads the excel file
df=pd.read_excel('board2.xlsx')

# calls the excel file
df
```

1a.

```python
#name of the file
Vis= df[(df['Hometown'] == 'Visayas') & (df['Math'] < 70)][['Name', 'Gender', 'Track', 'Math']]

#sorts the data where the Hometown is Visayas
df[(df['Hometown'] == 'Visayas')

#sorts the data where Math is less than 70
(df['Math'] < 70)]

#Outputs the Name,Gender,Track,Math where the conditions are met
[['Name', 'Gender', 'Track', 'Math']]

#Calls the filename
Vis
```

The code filters df to include only rows where Hometown is "Visayas" and Math is less than 70, selects the Name, Gender, Track, and Math columns, and saves the result to the variable Vis, with the help of pandas(remember:conditions on the left and output on the right).

<img width="220" height="92" alt="image" src="https://github.com/user-attachments/assets/a4f84be2-6299-4737-b836-1a31fcd7027e" />

1.b

```python
#Name of the file
Instru=df[(df['Track'] == 'Instrumentation') & (df['Hometown'] == 'Luzon') & (df['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]

#Sorts the data where Track is Instrumentation
df[(df['Track'] == 'Instrumentation')

#Sorts the data where hometown is Luzon
(df['Hometown'] == 'Luzon')

#Sorts the data where Electronics is greater than 70
(df['Electronics'] > 70)]

#Outputs the Name,GEAS,Electronics,where the conditions where met
[['Name', 'GEAS', 'Electronics']]
Instru
```

The code filters df to include only rows where Track is "Instrumentation", Hometown is "Luzon", and Electronics is greater than 70, then selects the Name, GEAS, and Electronics columns and stores the result in Instru,with the help of pandas(remember:conditions on the left and output on the right).

<img width="153" height="92" alt="image" src="https://github.com/user-attachments/assets/227c128f-37e7-4d27-853e-7c5bc3d04f39" />

1.c

```python
#Calculates tha average of grades or mean of the subjects using the .mean()function
df['Average'] = df[['Math', 'Electronics', 'GEAS','Communication']].mean(axis=1)

#Name of the file
Mindy = df[(df['Hometown'] == 'Mindanao') & (df['Gender'] == 'Female') & (df['Average'] >= 55)][['Name', 'Track', 'Electronics', 'Average']]

#sorts the data where hometown is Mindanao
df[(df['Hometown'] == 'Mindanao')

#sorts the data where gender is female
(df['Gender'] == 'Female')

#Sorts the average where it is greater than or equal to 55
(df['Average'] >= 55)]

#Outputs the Name,Track,Electronics,Average where the conditions where met
[['Name', 'Track', 'Electronics', 'Average']]

#Call the filename
Mindy
```

The code calculates each student’s average score across Math, Electronics, GEAS, and Communication, saves it in a new column called Average with the help of the function mean(), then filters df for female students from Mindanao with an average of 55 or higher, selecting only Name, Track, Electronics, and Average, and stores the result in Mindy.

<img width="245" height="131" alt="image" src="https://github.com/user-attachments/assets/28754df6-c1a0-4c0c-a775-1d07135c05e3" />

## Solution 2:Visualization
2.Before we start we must import seaborn and matplotlib.pyplot

```python
import matplotlib.pyplot as plt
import seaborn as sns
```

This will be used for functions of visualization.

2a.

```python
#Selects only these 4 columns from the dataframe and calculates the mean,mean(axis=1)because axis=1 means operate across columns,if 0 it would be rows
df['Average'] = df[['Math', 'Electronics', 'GEAS','Communication']].mean(axis=1)

#sns refers to seaborn and darkgrdid changes the overall appearance of your barplot/boxplot
sns.set(style="darkgrid")
```


```python
#plt uses matplotlib and figsize(10,6) means 10 inches of width and 6 inches of height
plt.figure(figsize=(10, 6))

#Draws a bar plot using seaborn and displays the Tracks on the horizontal axis and Average on the Vertical axis,and it gets its data from df
sns.barplot(x='Track', y='Average', data=df, errorbar=None)

#Names the barplot "Average grade by track"
plt.title('Average Grade by Track')

#Displays the completed barplot
plt.show()
```

The code creates a Seaborn bar chart showing the average grades (Average) for each track (Track) from the DataFrame df, with a custom figure size, no error bars, and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="599" height="369" alt="image" src="https://github.com/user-attachments/assets/2e82ee09-6fb8-40c7-9ff0-801b8fa59f1b" />

2b.

```python
#plt uses matplotlib and figsize(10,6) means 10 inches of width and 6 inches of height
plt.figure(figsize=(10, 6))

#Draws a bar plot using seaborn and displays the Gender on the horizontal axis and Average on the Vertical axis,and it gets its data from df
sns.barplot(x='Gender', y='Average', data=df, errorbar=None)

#Names the barplot "Average grade by gender"
plt.title('Average Grade by Gender')

#Displays the completed barplot
plt.show()
```

The code plots a Seaborn bar chart comparing the average grades (Average) for each gender (Gender) in the DataFrame df, using a 10×6 figure size, no error bars, and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="467" height="306" alt="image" src="https://github.com/user-attachments/assets/6ce11284-86a2-4ec6-abf8-d5f3d77dc327" />

2c.

```python
#plt uses matplotlib and figsize(10,6) means 10 inches of width and 6 inches of height
plt.figure(figsize=(10, 6))

#Draws a bar plot using seaborn and displays the Hometown on the horizontal axis and Average on the Vertical axis,and it gets its data from df
sns.barplot(x='Hometown', y='Average', data=df, errorbar=None)

#Names the barplot "Average grade by Hometown"
plt.title('Average Grade by Hometown')

#Displays the completed barplot
plt.show()
```

The code generates a Seaborn bar chart comparing the average grades (Average) of students grouped by their hometown (Hometown) from the DataFrame df, with a 10×6 figure size, no error bars, and a descriptive title.(With the help of matplotlib.pyplot and seaborn)

<img width="481" height="310" alt="image" src="https://github.com/user-attachments/assets/a6d415bb-d790-4e32-b82b-04c17ba2cbee" />

2d.

```python
#plt uses matplotlib and figsize(10,6) means 10 inches of width and 6 inches of height
plt.figure(figsize=(10, 6))

#Draws a box plot using seaborn and displays the Track on the horizontal axis and Average on the Vertical axis,and it gets its data from df
sns.boxplot(x='Track', y='Average', data=df)

#Names the boxplot "Average grade by Track"
plt.title('Distribution of Average Grades by Track')

#Displays the completed boxplot
plt.show()
```

This code creates a Seaborn box plot to display the distribution of average grades (Average) for each track (Track) in the DataFrame df, using a 10×6 figure size and adding a title.(With the help of matplotlib.pyplot and seaborn)

<img width="487" height="307" alt="image" src="https://github.com/user-attachments/assets/e05488c4-df9e-47c4-8b0a-581eba73a155" />

2e.

```python
plt.figure(figsize=(10, 6))
sns.boxplot(x='Gender', y='Average', data=df)
plt.title('Distribution of Average Grades by Gender')
plt.show()
```

This code produces a Seaborn box plot showing how average grades (Average) are distributed across genders (Gender) in the DataFrame df, with a 10×6 figure size and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="487" height="301" alt="image" src="https://github.com/user-attachments/assets/8a245b2d-c4db-4bbb-9168-0898d7dad532" />

2f.

```python
plt.figure(figsize=(10, 6))
sns.boxplot(x='Hometown', y='Average', data=df)
plt.title('Distribution of Average Grades by Hometown')
plt.show()
```

This code creates a Seaborn box plot that visualizes the distribution of average grades (Average) for each hometown (Hometown) in the DataFrame df, using a 10×6 figure size and adding a descriptive title.(With the help of matplotlib.pyplot and seaborn)

<img width="481" height="311" alt="image" src="https://github.com/user-attachments/assets/4d868a53-82eb-413d-bb9f-3910dae12894" />
