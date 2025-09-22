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

The code filters df to include only rows where Hometown is "Visayas" and Math is less than 70, selects the Name, Gender, Track, and Math columns, and saves the result to the variable Vis.

<img width="220" height="92" alt="image" src="https://github.com/user-attachments/assets/a4f84be2-6299-4737-b836-1a31fcd7027e" />

1.b
