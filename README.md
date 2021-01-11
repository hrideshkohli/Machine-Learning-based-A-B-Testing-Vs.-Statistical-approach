# Machine-Learning-based-A-B-Testing-Vs.-Statistical-approach

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

``` Treatment Group (Group A) - This group is exposed to the new web page, popup form, etc.

Control Group (Group B) - This group experiences no change from the current setup.```

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

Experiment Data(https://www.kaggle.com/tammyrotem/experiment-data) ```
