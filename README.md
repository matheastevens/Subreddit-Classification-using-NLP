Jupyter Notebook
README.md
a minute ago
GitHub Flavored Markdown
File
Edit
View
Language
ovide insight into cultural interpreations of market forces. 
1
# Text Comparison, Classification and Analysis:
2
### How language in subreddits can be identified, classified and used to predict market trends.
3
​
4
## Executive Summary
5
​
6
This project started during the earliest days of the [WallStreetBets](https://www.reddit.com/r/wallstreetbets/) GameStop mania. In late January of 2021,  an army of individual traders spurred on by Reddit discourse surged the salesprice of GameStop stock in an effort to squeeze hudge funds holding stock shorts. In a matter of days, the stock rose from around $20 USD to over $450 USD, catching media attention around the world. 
7
​
8
Prior to this event, the WallStreetBets subreddit is known for their crass language and bullish positions in the market. The subreddit is a place to share thoughts regarding the stock market and individual investing options. In some ways the [Personal Finance Canada](https://www.reddit.com/r/PersonalFinanceCanada/) subreddit is similar in that it is a home to Canadian individual investors looking for investment advice. While the two subreddits discuss similar topics, the language used can be very different. 
9
​
10
To gain some insight into why WallStreetBets was the subreddit of choice for GameStop bolstering and how it differed from more conventional individual investment threads, I developed a natural laguage processing algorithm to classify whether a post originated from WallStreetBets or Personal Finance Canada. The algorithm can predict with 94% accuracy the origin of the post, as well as determine keywords which differentiate the two subreddits. 
11
​
12
#### Initial model building and results
13
​
14
Subreddit text was scraped using the [Pushshift API](https://pushshift.io/api-parameters/) on January 23rd, 2021. The text was preproccessed using scikit-learn's various vecotizers, and used to test a variety of classification algorithms (pictured right). 
15
​
16
Using a training and testing split, we evaluated each model by measuring the accuracy, precision and recall scores, pictured below. 
17
​
18
While the Support Vector Machine model performed very well, we will look at the results of the logistic regression model for interpretable findings. 
19
​
20
#### Feature Importance
21
​
22
Through calculating the feature importance with scikit-learn's permutation importance, we can see which words have the largest effect on the model's score, indicating how much the model depends on a word to make a correct prediction. 
23
​
24
Some of the biggest findings include:
25
 - The word gme is by far the most important feature in determining a posts origin.
26
 
27
The word gme has the highest permutation importance score with the logistic regression model. This defining feature raises some flags regarding the model's ability to classify posts beyond the Gamestop mania. While it may be a strong indication of subreddit+ origin now, it may no longer be present in either subreddit in the future, limiting our model's long-term performance and generalization power.  
28
 
29
 - Canadian and American-specific investment terms are important features. 
30
Canadian-specific investment terms like tfsa and ei came up in the feature permutation calculations. Because Canadian Personal Investor subreddit is, afterall, dedicated to the personal wealth of Canadians, it is unsurprising that these words are indicative of which class a post comes from.
31
​
32
 - Industry terminology as important features.
33
While it is unsurprising that words like tfsa and ei are important words, it is interesting that industry terminology is also picked up as important words. Words like currency, immigration and oil have a degree of importance on model accuracy have a measurable effect on the model's accuracy. Even basic domain knowledge would understand that the price of oil, immigration policies and currency valuations impact markets around the world. Further exporation into why these are therefore distinguishing words between subreddits could provide insight into cultural interpreations of market forces.  
34
​
35
 - Derogatory language as one of the feature words leverage by the model to classify posts.
36
 
37
 WallStreetBets is not moderated for crass language, and it is known to have derogatory language in it's posts. The model, however, can pick up on the frequency of derogatory language used in one subreddit, and the lack of derogatory language in another. 
38
​
39
​
40
#### Final Thoughts
41
​
42
This project is intended to be an intial exploration into leveraging data available on Reddit to develop classification algorithms. There could be potential to develop this idea further by scraping more data before the Gamestop mania and establishing a more generalizable predictive model. Given the feature importances calculated for the logistic regression model developed on a small sample of data, it is clear that while the model performs well during height of Gamestop, the features used to train the model may not be the best for a long-term predictive model.  
43
​
44
​
