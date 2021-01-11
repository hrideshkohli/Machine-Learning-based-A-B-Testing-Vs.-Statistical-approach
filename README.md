# Machine-Learning-based-A-B-Testing-Vs.-Statistical-approach

![alt text](https://github.com/hrideshkohli/Machine-Learning-based-A-B-Testing-Vs.-Statistical-approach/blob/main/AB-Testing.png)

## Few popular hashtags -
**#ABTesting #Machine Learninig #Linear Regression
#Learning Recommendation #Decision Tree #XGBoost**

# Motivation
With the rise of digital marketing led by tools including Google Analytics, Google Adwords, and Facebook Ads, a key competitive advantage for businesses is using A/B testing to determine effects of digital marketing efforts. Why? In short, small changes can have big effects.

This is why A/B testing is a huge benefit. A/B Testing enables us to determine whether changes in landing pages, popup forms, article titles, and other digital marketing decisions improve conversion rates and ultimately customer purchasing behavior. A successful A/B Testing strategy can lead to massive gains - more satisfied users, more engagement, and more sales - Win-Win-Win.

# About the Project
A major issue with traditional, statistical-inference approaches to A/B Testing is that it only compares 2 variables - an experiment/control to an outcome. The problem is that customer behavior is vastly more complex than this. Customers take different paths, spend different amounts of time on the site, come from different backgrounds (age, gender, interests), and more. This is where Machine Learning excels - generating insights from complex systems.

In this project, I will compare outputs of both statistical and Machine Learning based A/B testing approach.

# Steps involved in this project

## 1.0 What is A/B Testing?

A/B Testing is a tried-and-true method commonly performed using a traditional statistical inference approach grounded in a hypothesis test (e.g. t-test, z-score, chi-squared test). In plain English, 2 tests are run in parallel:

``` 
Treatment Group (Group A) - This group is exposed to the new web page, popup form, etc.

Control Group (Group B) - This group experiences no change from the current setup. 
```

The goal of the A/B is then to compare the conversion rates of the two groups using statistical inference.

* The problem is that the world is not a vacuum involving only the experiment (treatment vs control group) and effect. The situation is vastly more complex and dynamic. Consider these situations:

* Users have different characteristics: Different ages, genders, new vs returning, etc

* Users spend different amounts of time on the website: Some hit the page right away, others spend more time on the site

* Users are find your website differently: Some come from email or newsletters, others from web searches, others from social media

* Users take different paths: Users take actions on the website going to different pages prior to being confronted with the event and goal

Often modeling an A/B test in this vacuum can lead to misunderstanding of the true story.

## 2.0 Why use Machine Learning?

Unlike statistical inference, Machine Learning algorithms enable us to model complex systems that include all of the ongoing events, user features, and more. There are a number of algorithms each with strengths and weaknesses.

'An attractive benefit to Machine Learning is that we can combine multiple approaches to gain insights.'

Rather than discuss in abstract, we can use an example from Udacity’s A/B Testing Course, but apply the applied Machine Learning techniques from our Business Analysis with R Course to gain better insights into the inner-workings of the system rather than simply comparing an experiment and control group in an A/B Test.

## 3.0 A/B Test Using Machine Learning: Step-By-Step Walkthrough

# Experiment Name: “Free Trial” Screener

---

In the experiment, "Audacity" tested a change where if the student clicked “start free trial”, they were asked how much time they had available to devote to the course.

If the student indicated 5 or more hours per week, they would be taken through the checkout process as usual. If they indicated fewer than 5 hours per week, a message would appear indicating that Udacity courses usually require a greater time commitment for successful completion.

Why Implement the Form?

The goal with this popup was that this might set clearer expectations for students upfront, thus reducing the number of frustrated students who left the free trial because they didn’t have enough time.

However, what Audacity wants to avoid is “significantly” reducing the number of students that continue past the free trial and eventually complete the course

## Project Goal
` In this analysis, we will investigate which features are contributing enrollments and determine if there is an impact on enrollments from the new “Setting Expectations” form.

The users that experience the form will be denoted as “Experiment = 1” The control group (users that don’t see the form) will be denoted as “Experiment = 0”.`

# 3.1 Get the Data

``` The data set for this A/B Test can be retrieved from Kaggle Data Sets.

Control Data(https://www.kaggle.com/tammyrotem/control-data)

Experiment Data(https://www.kaggle.com/tammyrotem/experiment-data) 
```

## Investigate the Data
We have 5 columns consisting of:

Date: a character formatted Day, Month, and Day of Month Pageviews: An aggregated count of Page Views on the given day Clicks: An aggregated count of Page Clicks on the given day for the page in question Enrollments: An aggregated count of Enrollments by day. Payments: An aggregated count of Payments by day.

## Key Points
37 total observations in the control set and 37 in the experiment set

Data is time-based and aggregated by day - This isn’t the best way to understand complex user behavior, but we’ll go with it

We can see that Date is formatted as a character data type. This will be important when we get to data quality. We’ll extract day of the week features out of it.

Data between the experiment group and the control group is in the same format. Same number of observations (37 days) since the groups were tested in parallel

## Data Quality Check
Next, let’s check the data quality. We’ll go through a process involves:

```
Check for Missing Data - Are values missing? What should we do?
``` 
Check Data Format - Is data in correct format for analysis? Are all features created and in the right class?

## Check for Missing Data
Key Point: We have 14 days of missing observations that we need to investigate

Key Point: The count of missing data is consistent (a good thing). We still need to figure out what’s going on though.

Key Point: We don’t have Enrollment information from November 3rd on. We will need to remove these observations.

## Check Data Format
**Key Points:**

Date is in character format. It doesn’t contain year information. Since the experiment was only run for 37 days, we can only realistically use the “Day of Week” as a predictor.

The other columns are all numeric, which is OK. We will predict the number of Enrollments (regression)

Payments is an outcome of Enrollments so this should be removed

## Format Data
Now that we understand the data, let’s put it into the format we can use for modeling. We’ll do the following:

- Combine the control_tbl and experiment_tbl, adding an “id” column indicating if the data was part of the experiment or not-
- Add a “row_id” column to help for tracking which rows are selected for training and testing in the modeling section
- Create a “Day of Week” feature from the “Date” column
- Drop the unnecessary “Date” column and the “Payments” column
- Handle the missing data (NA) by removing these rows.
- Shuffle the rows to mix the data up for learning
- Reorganize the columns

## Training and Testing Sets
With the data formatted properly for analysis, we can now separate into training and testing sets using an 80% / 20% ratio. We can use the initial_split() function from rsample to create a split object, then extracting the training() and testing() sets.

## Implement Machine Learning Algorithms
We’ll implement the new parsnip R package. For those unfamiliar, here are some benefits:

Our strategy will be to implement 2 modeling approaches:
- Linear Regression
- Decision tree
- Random Forest

# Conclusion

## - Linear Regression had coefficient of -15 for experiment column stating that when experiment=1, enrollments reduce by 15 per day.
## - Decision Tree/RandomForest show that information gain for PageViews and clicks account for 80% whereas experiment account for 17%.

Hence, we can clearly see that from machine learning models too, we can correlate and come up with the results related to A/B testing.


✉️ Feel free to contact me @ hridesh1987@gmail.com
