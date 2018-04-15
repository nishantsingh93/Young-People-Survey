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
* For convenience, the original variable names were shortened in the data file. See the columns.csv file if you want to match the data with the original names.
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
![imp](https://user-images.githubusercontent.com/25557540/38773153-0bd1f1f2-3ffb-11e8-9a68-a3763fa2896e.png)
![ivsin](https://user-images.githubusercontent.com/25557540/38773154-0beadbb8-3ffb-11e8-8bb5-7ac34c81b50b.png)
![lvl](https://user-images.githubusercontent.com/25557540/38773155-0c02659e-3ffb-11e8-91f0-1c202a5fc53b.png)
![lvo](https://user-images.githubusercontent.com/25557540/38773156-0c1ac260-3ffb-11e8-9fcd-de59dd6d8fc5.png)
![mcvl](https://user-images.githubusercontent.com/25557540/38773157-0c32513c-3ffb-11e8-8777-36517774185a.png)
![nvl](https://user-images.githubusercontent.com/25557540/38773158-0c4a9936-3ffb-11e8-9952-b17663f4a64f.png)
![ovl](https://user-images.githubusercontent.com/25557540/38773159-0c633aae-3ffb-11e8-9337-51bc1e80dd6f.png)


******************************************************************************************************************************
******************************************************************************************************************************
### IV. Training Machine Learning Algorithms:

![correlationplot](https://user-images.githubusercontent.com/25557540/38773148-0b594338-3ffb-11e8-8e57-75c4ae59cda1.png)

![heatplot](https://user-images.githubusercontent.com/25557540/38773151-0ba24c4a-3ffb-11e8-877d-8377471807b9.png)


#### Logestic Regression 
******************************************************************************************************************************
1. weewewe
2. 2eewe


#### Clustering 

******************************************************************************************************************************
******************************************************************************************************************************

### V. Conclusion:


******************************************************************************************************************************
******************************************************************************************************************************
### VI. Future Enhancements:

******************************************************************************************************************************
******************************************************************************************************************************
### VII. References:

* https://www.themoviedb.org/
* https://drsimonj.svbtle.com/ridge-regression-with-glmnet
* https://www.r-bloggers.com/ridge-regression-and-the-lasso/
* https://www.r-bloggers.com/random-forests-in-r/





