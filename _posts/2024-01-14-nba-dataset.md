---
layout: post
title: Lab 4 - Michael Jordan's Career
subtitle: Analyzing Statistics of Michael Jordan
cover-img: /assets/img/michael-jordan-through-the-years-14.jpg.webp
thumbnail-img: /assets/img/Michael-Jordan.jpg.webp
share-img: /assets/img/michael-jordan-through-the-years-14.jpg.webp
tags: [books, test]
---
## 1. Which dataset did you work with?
I compiled the main statistics of Michael Jordan's career off of Basketball Reference.

## 2. Which aspect of this dataset are you interested in? What do you hope to learn from analyzing this dataset?
I wanted to understand the career of Michael Jordan more. After arguing with Gray about who the greatest player of all time was, I wanted to use the summary statitics using Pandas to analyze Michael Jordan's career, proving he is the best player ever. I kept the statistics that were important when deciding who the greatest ever was, and I added some advanced stats that I thought were interesting as well.

## 3.1: The variables you looked at
The variables I had in my data set included: 
Season
Age
Team
League
Position
Games
Games Started
Minutes Played
Field Goals
Field Goals Attempted	
Field Goal Percentage	
3 pointers	
3 pointers attempted
3 point percentage	
Player Efficiency Rating
True Shooting Percentage
Box Plus/Minus	
Efficient Field Goal Percentage
Free Throws
Free Throws Attemped
Free Throw Percentage
Offensive Rebounds
Defensive Rebounds
Total Rebounds
Assists
Steals
Blocks
Turnovers
Personal Fouls
Points

Although, I had a lot of variables, I believe each one contributed to the importance of Jordan's career.

## 3.2: Distributions of variables (center and variability)

![output](https://github.com/ahaanm1/beautiful-jekyll/assets/114838648/0b98e160-0a8d-4d9b-9886-40800247df11)

These graphs contain 6 different boxplots for 6 of the primary variables I wanted to highlight. It gives the center which is consistent with the career averages for each of those seasons. It also gives the variability by showing how far the first and third quartiles and the minimum and maximum are from the middle line. For example, on blocks you can see the max is high showing that his average blocks per season were typically low but he had one amazing season.

## 3.3: Relationships between variables and Visualizations of the dataset

This graph shows a scatter pair plot for 6 different variables
![points](https://github.com/ahaanm1/beautiful-jekyll/assets/114838648/69b7f1d8-96b3-4948-b760-386ba0161b24)

This is the code I used to output the correlation matrix.
~~~
correlation_matrix = data[variables].corr()
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title("Correlation of Variables")
plt.show()
~~~
This graph shows the correlation of each of the scatter plots.
![corr](https://github.com/ahaanm1/beautiful-jekyll/assets/114838648/382c2134-dcb9-481e-bfa5-cf4dd8b08ac4)

These graphs gave lots of insightful information about Michael Jordan. For example what immediately came to my mind was that the Rebounds and Blocks were oppositely correlated. This surprised me heavily because typically if you are rebounding a lot you will be in the paint, which means you block more. However, after double checking on basketball reference, it was clear that Michael Jordan rebounded more when he blocked less and vice versa. Another aspect that I found interesting was that points and steals were very correlated which meant that he got a lot of steals when he scored a lot. This makes sense because he could get points off turnovers from his own steals. Finally, a third part of this dataset that particularly intriguied me was that Jordan's points and field goal percentage were somewhat correlated. I wasn't expecting this because the more shots you put up the less likely you are to maintain a good shooting percentage but Jordan was so great that he could.

## 3.5: Limitations of the Dataset

One limitation of my dataset is that I am analyzing Michael Jordan in isolation. This means that there is nothing I can compare his statistics to. This comparative context is important for understanding the player's standing and impact in basketball. 

Another limitation could be variable limitation because there are some variables I did not include which could impact a player's legacy such as rings and finals appearances.

## 3.6: What conclusions can you draw about this dataset? What is your supporting evidence? Your blog post should showcase your understanding of the material covered in this unit.


From this dataset I was able to learn about how great Michael Jordan was. However, I also gathered specific information about different metrics that enlightened me about new information regarding Michael Jordan. For example, using these 2 graphs:

![outputs](https://github.com/ahaanm1/beautiful-jekyll/assets/114838648/3147a6d7-453d-43be-81ce-7e5b51fce89d)

Looking at 1996 and 1997, Michael Jordan's true shooting percentage was much higher in relation to the rest of his seasons then his field goal percentage. By noticing this difference I understood that Michael Jordan's 3 point and free throw percentages would be much higher than his field goal for those 2 seasons. So I searched up why Michael Jordan shot better in 1996 and 1997, and actually it is because the NBA made the 3 point line closer for those years which is why Jordan's true shooting percentage was higher than it should've been.

Another graph that gave me insight into Michael Jordan's career was a boxplot of Jordan's games played per season.

![GAME](https://github.com/ahaanm1/beautiful-jekyll/assets/114838648/f207af88-475e-4aa5-a1c7-a236369864a9)

This graph was interesting because it demonstrated how consistent Jordan's games played were since there is only 82 games in the season and he consistently had around 80 games per season, However, the outliers are visible at one season with 60 games and 2 seasons with under 20 games. This graph makes clear how significant injuries are to a player's career.
