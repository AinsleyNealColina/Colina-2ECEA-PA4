# Colina-2ECEA-PA4

## Objectives
1.To identify the codes and functions needed in cleaning and visualizing data

2.To be able to apply and use the different codes and functions in creating a Python program that will 
be used in data wrangling and data visualization.

## Problem 1: Data Frames

So we are tasked to:

1a.Display the data [Name,Gender,Track,Math]. With the condition of Hometown is Visayas and Math less than 70, and name it Vis.

1b.Dispaly the data [Name,GEAS,Electronics].With the condition of Track is instrumentation,Hometown is Luzon, Electronics greater than 70,and name it Instru.

1c.Display the data [Name,Track,Electronics,Average].With the condition of hometown is Mindanao, gender is female, and average >=55,and name it Mindy.

2.Create a visualization that shows how the different features contributes to average grade. Does 
chosen track in college, gender, or hometown contributes to a higher average score? 

Steps:

1a.

`
Vis = df[(df['Hometown'] == 'Visayas') & (df['Math'] < 70)][['Name', 'Gender', 'Track', 'Math']]
Vis
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

This code creates a Seaborn bar chart showing the average grades (Average) for each track (Track) from the DataFrame df, with a custom figure size, no error bars, and a title.

<img width="599" height="369" alt="image" src="https://github.com/user-attachments/assets/2e82ee09-6fb8-40c7-9ff0-801b8fa59f1b" />
