# Young People Survey
******************************************************************************************************************************
******************************************************************************************************************************
### I. Introduction:

**Dataset:** 
This Project aims at predicting behaviour patterns in young adults using supervised learning approach. The [Young People Survey](https://www.kaggle.com/miroslavsabo/young-people-survey/data) dataset is a survey conducted in the UK.The dataset is divided into 2 csv files.


**Objective:** 

**Below are the following questions are needed to be answered:**
* Given the music preferences, do people make up any clusters of similar behavior?
* Do women fear certain phenomena significantly more than men? Do the left handed people have different interests than right handed?
* Can we predict spending habits of a person from his/her interests and movie or music preferences?
* Can we describe a large number of human interests by a smaller number of latent concepts?
* Are there any connections between music and movie preferences?
* How to effectively visualize a lot of variables in order to gain some meaningful insights from the data?
* Small number of participants often cheats and randomly answers the questions. Can you identify them? Hint: Local outlier factor may help.
* Are there any patterns in missing responses? What is the optimal way of imputing the values in surveys?
* If some of user's interests are known, can we predict the other? Or, if we know what a person listen, can we predict which kind of movies he/she might like?


******************************************************************************************************************************
******************************************************************************************************************************
### II. Data Preparation:

**About the Dataset:**

* In 2013, students of the Statistics class at FSEV UK were asked to invite their friends to participate in this survey.
* The data file (responses.csv) consists of 1010 rows and 150 columns (139 integer and 11 categorical).
* For convenience, the original variable names were shortened in the data file. 
* The data contain missing values.
* The survey was presented to participants in both electronic and written form.
* The original questionnaire was in Slovak language and was later translated into English.
* All participants were of Slovakian nationality, aged between 15-30.
* The variables can be split into the following groups:
* Music preferences (19 items)
* Movie preferences (12 items)
* Hobbies & interests (32 items)
* Phobias (10 items)
* Health habits (3 items)
* Personality traits, views on life, & opinions (57 items)
* Spending habits (7 items)
* Demographics (10 items)

******************************************************************************************************************************
**Dataset Cleaning:**

**Common data cleaning steps:**

* <b>1)</b> dropna() - Used to drop the columns where any element is nan.
* <b>1)</b> Get_dummies () - This helps in converting categorical variables into dummy/indicator variables

* Sample Code: 
```
responses4 = pd.get_dummies(columns=['Smoking', 'Punctuality', 'Lying','Alcohol', 'Internet usage', 'Gender', 'Left - right handed', 'Education', 'Only child', 'Village - town', 'House - block of flats'],data=responses)
```
******************************************************************************************************************************
******************************************************************************************************************************
### III. Exploratory Analysis:

![wcloud](https://user-images.githubusercontent.com/25557540/38773162-0cadb750-3ffb-11e8-9f09-ab13c7baa3ad.png)
![fvl](https://user-images.githubusercontent.com/25557540/38773150-0b88ff92-3ffb-11e8-9cf8-8abfefb67301.png)
![hvv](https://user-images.githubusercontent.com/25557540/38773152-0bb9bf7e-3ffb-11e8-9762-c33f02eecd7d.png)


![lvo](https://user-images.githubusercontent.com/25557540/38773156-0c1ac260-3ffb-11e8-9fcd-de59dd6d8fc5.png)
![mcvl](https://user-images.githubusercontent.com/25557540/38773157-0c32513c-3ffb-11e8-8777-36517774185a.png)
![nvl](https://user-images.githubusercontent.com/25557540/38773158-0c4a9936-3ffb-11e8-9952-b17663f4a64f.png)
![ovl](https://user-images.githubusercontent.com/25557540/38773159-0c633aae-3ffb-11e8-9337-51bc1e80dd6f.png)


******************************************************************************************************************************
******************************************************************************************************************************
### IV. Training Machine Learning Algorithms:

![correlationplot](https://user-images.githubusercontent.com/25557540/38773148-0b594338-3ffb-11e8-8e57-75c4ae59cda1.png)

![heatplot](https://user-images.githubusercontent.com/25557540/38773151-0ba24c4a-3ffb-11e8-877d-8377471807b9.png)

**Following are the insights I plan to explore in this dataset:**

1. Lonliness - What are the factors contributing in a person's feeling of Lonliness.
2. Life Struggles - Height and weight ? - Who is struggling more in their life.
3. Drinkers vs Non-drinkers - Predicting based on person's choices and character traits.

**To do the analysis on the above mentioned areas the following Machine Learning Techniques:**

1. Lonliness - Logistic Regression
2. Life Struggles - Relationship with Height and Weight ? - Logistic Regression
3. Drinkers and Non-drinkers - Decision Tree
******************************************************************************************************************************
 **Logestic Regression - Loneliness:**

* In this analysis, I am trying to use logistic regression to check wether I can get an interesting insight related to Loneliness. Also, I would like to see which all features can be attributed towards Loneliness.
* For this analysis the following steps were performed:
1. Null values were removed. This step was done as a common step at the top.
2. The dummies variables were created from the categorical variables.
3. Creating two data frames males and females for the purpose of visualising

**Result:**

![ivsin](https://user-images.githubusercontent.com/25557540/38773154-0beadbb8-3ffb-11e8-8bb5-7ac34c81b50b.png)

**How to predict a young person’s loneliness?:**
* Firstly I transformed our original loneliness variable to a dummy variable.
* Loneliness > 3 are considered as lonely.
* Loneliness<=3 are considered not lonely.
* Using  logistic regression model with 71 variables, I can predict a person’s loneliness level at an accuracy rate of 71% with (K-fold) test sets.
* The variables with largest coefficients can be found in above figure.
* Pepople who like writing, have fear of public speaking, surfs a lot on internet,enjoys using PC & spends a lot on gadgets can have high degree of Loneliness whereas if they like spending time with friends, likes active sports, geography, pets & entertainment are negatively related with Loneliness


******************************************************************************************************************************
 **Logestic Regression - Life Struggles:**

* In this analysis, I am trying to use logistic regression to check wether we can get an interesting insight related to Life Struggles.
* Also,I would like to see which all features can be attributed towards Life struggles.

* For this analysis the following steps were performed:

1. Null values were removed. This step was done as a common step at the top.
2. The dummies variables were created from the categorical variables.
2. Finding the highest correlations.
3. Trying to find the reasons behind those correlations.

**Result:**

* The most correlated features are Height and Weight which are self-explanaroty. 
* People who are interested in Biology are also interested in Medicine and Chemistry. 
* The same for Fantasy/Fairy tales and Animated movies.
* one might ask why there is a negative correlation between Life struggles, Weight and Height. Let's explore further to understand the reasons behind this correlation.
* If i observe the correlations of Life struggles, and hight and weight, I will see that these three variables are highly correlated with gender
![imp](https://user-images.githubusercontent.com/25557540/38773153-0bd1f1f2-3ffb-11e8-9a68-a3763fa2896e.png)

* If you have more life struggles in life, you are probably a woman :) Of course, if you like shopping, you are more likely to be a woman. 
* But if you are tall, or weigh a lot or like "PC Software, Hardware" then you are probably a man.
* Negative correlation between Life struggles and height/weight was due to the female and male separation.





******************************************************************************************************************************
**Decision Tree:**

* In this analysis, I have tried a decision tree as a machine learning technique to check wether I can get an interesting insight or not related to drinkers and non-drinkers.
* For this analysis the following steps were performed:
1. Null values were removed. This step was done as a common step at the top.
2. The dummies variables were created from the categorical variables.
3. A function is written to replace the string with numbers in the field Alcohol and store it in a new column Alcohol2.
4. A decision tree with depth 3 was created.

**Result:**
![espe](https://user-images.githubusercontent.com/25557540/38773149-0b71a46e-3ffb-11e8-90d9-bf9a53967117.png)

* It was surprising to find that teenagers of age 15-16 tend to drink more even though they are not legally allowed to do so. * Underage drinking is a serious public health problem in the society. 
* According to a study, Britain has the fourth highest levels of underage drinking among 15-years-olds. 
* Parents and public welfare organizations can work together to fight this issue by focusing on the factors in the above analysis.
******************************************************************************************************************************
******************************************************************************************************************************
### V. Conclusion:

**Loneliness:** The Co-op Foundations and charitable organizations working to prevent and tackle youth loneliness can take these factors into consideration to help young people form stronger connections within their community.

**Life Struggles:** Please take care of females! It is the moral responsibility of everyone to treat women with respect and dignity as they already have a lot of struggles.

**Drinkers vs Non-drinkers:** It was surprising to find that teenagers of age 15-16 tend to drink more even though they are not legally allowed to do so. Underage drinking is a serious public health problem in the society. According to a study, Britain has the fourth highest levels of underage drinking among 15-years-olds. Parents and public welfare organizations can work together to fight this issue by focusing on the factors in the above analysis.


******************************************************************************************************************************
******************************************************************************************************************************
### VI. Future Enhancements:

******************************************************************************************************************************
******************************************************************************************************************************
### VII. References:






