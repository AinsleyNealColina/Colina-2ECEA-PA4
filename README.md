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
## Problem 1:Data Frames
1a.

`
Vis-name of the file
df[(df['Hometown'] == 'Visayas')-sorts the data where the Hometown is Visayas
(df['Math'] < 70)]-sorts the data where Math is less than 70
[['Name', 'Gender', 'Track', 'Math']]-Outputs the Name,Gender,Track,Math where the conditions are met
Vis-calls the filename
`

The code filters df to include only rows where Hometown is "Visayas" and Math is less than 70, selects the Name, Gender, Track, and Math columns, and saves the result to the variable Vis, with the help of pandas(remember:conditions on the left and output on the right).

<img width="220" height="92" alt="image" src="https://github.com/user-attachments/assets/a4f84be2-6299-4737-b836-1a31fcd7027e" />

1.b

`
Instru = df[(df['Track'] == 'Instrumentation') & (df['Hometown'] == 'Luzon') & (df['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]
Instru
`

The code filters df to include only rows where Track is "Instrumentation", Hometown is "Luzon", and Electronics is greater than 70, then selects the Name, GEAS, and Electronics columns and stores the result in Instru,with the help of pandas(remember:conditions on the left and output on the right).

<img width="153" height="92" alt="image" src="https://github.com/user-attachments/assets/227c128f-37e7-4d27-853e-7c5bc3d04f39" />

1.c

`
df['Average'] = df[['Math', 'Electronics', 'GEAS','Communication']].mean(axis=1)
Mindy = df[(df['Hometown'] == 'Mindanao') & (df['Gender'] == 'Female') & (df['Average'] >= 55)][['Name', 'Track', 'Electronics', 'Average']]
Mindy
`

The code calculates each student’s average score across Math, Electronics, GEAS, and Communication, saves it in a new column called Average with the help of the function mean(), then filters df for female students from Mindanao with an average of 55 or higher, selecting only Name, Track, Electronics, and Average, and stores the result in Mindy.

<img width="245" height="131" alt="image" src="https://github.com/user-attachments/assets/28754df6-c1a0-4c0c-a775-1d07135c05e3" />

## Problem 2:Visualization

2a.

`
df['Average'] = df[['Math', 'Electronics', 'GEAS','Communication']].mean(axis=1)
sns.set(style="darkgrid")
`

`
plt.figure(figsize=(10, 6))
sns.barplot(x='Track', y='Average', data=df, errorbar=None)
plt.title('Average Grade by Track')
plt.show()
`

The code creates a Seaborn bar chart showing the average grades (Average) for each track (Track) from the DataFrame df, with a custom figure size, no error bars, and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="599" height="369" alt="image" src="https://github.com/user-attachments/assets/2e82ee09-6fb8-40c7-9ff0-801b8fa59f1b" />

2b.

`
plt.figure(figsize=(10, 6))
sns.barplot(x='Gender', y='Average', data=df, errorbar=None)
plt.title('Average Grade by Gender')
plt.show()
`

The code plots a Seaborn bar chart comparing the average grades (Average) for each gender (Gender) in the DataFrame df, using a 10×6 figure size, no error bars, and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="467" height="306" alt="image" src="https://github.com/user-attachments/assets/6ce11284-86a2-4ec6-abf8-d5f3d77dc327" />

2c.

`
plt.figure(figsize=(10, 6))
sns.barplot(x='Hometown', y='Average', data=df, errorbar=None)
plt.title('Average Grade by Hometown')
plt.show()
`

The code generates a Seaborn bar chart comparing the average grades (Average) of students grouped by their hometown (Hometown) from the DataFrame df, with a 10×6 figure size, no error bars, and a descriptive title.(With the help of matplotlib.pyplot and seaborn)

<img width="481" height="310" alt="image" src="https://github.com/user-attachments/assets/a6d415bb-d790-4e32-b82b-04c17ba2cbee" />

2d.

`
plt.figure(figsize=(10, 6))
sns.boxplot(x='Track', y='Average', data=df)
plt.title('Distribution of Average Grades by Track')
plt.show()
`

This code creates a Seaborn box plot to display the distribution of average grades (Average) for each track (Track) in the DataFrame df, using a 10×6 figure size and adding a title.(With the help of matplotlib.pyplot and seaborn)

<img width="487" height="307" alt="image" src="https://github.com/user-attachments/assets/e05488c4-df9e-47c4-8b0a-581eba73a155" />

2e.

`
plt.figure(figsize=(10, 6))
sns.boxplot(x='Gender', y='Average', data=df)
plt.title('Distribution of Average Grades by Gender')
plt.show()
`

This code produces a Seaborn box plot showing how average grades (Average) are distributed across genders (Gender) in the DataFrame df, with a 10×6 figure size and a title.(With the help of matplotlib.pyplot and seaborn)

<img width="487" height="301" alt="image" src="https://github.com/user-attachments/assets/8a245b2d-c4db-4bbb-9168-0898d7dad532" />

2f.

`
plt.figure(figsize=(10, 6))
sns.boxplot(x='Hometown', y='Average', data=df)
plt.title('Distribution of Average Grades by Hometown')
plt.show()
`

This code creates a Seaborn box plot that visualizes the distribution of average grades (Average) for each hometown (Hometown) in the DataFrame df, using a 10×6 figure size and adding a descriptive title.(With the help of matplotlib.pyplot and seaborn)

<img width="481" height="311" alt="image" src="https://github.com/user-attachments/assets/4d868a53-82eb-413d-bb9f-3910dae12894" />
