---
layout: post
title:  Salary Prediction Analysis
date:   2022-08-03
description: Using a Kaggle dataset, I set out to predict whether a person makes less than or equal to $50k or more. 
---

<p class="intro"><span class="dropcap">As</span> a final project nearing the end of my Data Science bootcamp, we were tasked to find our very own dataset. In sourcing a viable dataset, we had to make sure it was something of interest to us and to our audience (pretend stakeholders). The idea was to determine whether a person makes less or equal to $50k or more a year. Taking many features into account; such as gender, education, age, etc. We will use old census data to predict whether a person falls into either category. While considering that the data in itself is older(1994) and that it does present an imbalance when it comes to gender. Let's dive right in!</p>

# Data Load

## Data Cleaning

### Data Preprocessing 

#### Data Modeling

##### Results


<blockquote>Above in the highlighted text we can see the main components to which I make use of in this analysis, essentially being the steps taken to get the necessary results. The project includes Supervised Learning and it is categorized as a classification problem. We'll preview some of the code needed to make my prediction but first let's go over some terminology that may not be too clear to our core audience.</blockquote>

More specifically, we will be defining what supervised learning and what classification means in order to allow understanding for all who view this post.

## Definition List
<dl>
  <dt>Supervised Learning is</dt>
  <dd><a href="https://www.ibm.com/cloud/blog/supervised-vs-unsupervised-learning">Internet Definition</a>: A machine learning approach that’s defined by its use of labeled datasets. These datasets are designed to train or “supervise” algorithms into classifying data or predicting outcomes accurately. Using labeled inputs and outputs, the model can measure its accuracy and learn over time. <br><br><i><b>To note</b>: Supervised Learning can be split into two subcategories; one being Classification(mentioned below) and the other Regression.</i></dd>
  <dt>Classification</dt>
  <dd>The simplest way to explain this is using the simplest classification task, the binary classification. The model makes a prediction between two classes, for example, a binary prediction might be yes or no. A very common classification task would be predicting whether unseen emails are to be considered spam or not spam. <br><br>There are also multi-class classification tasks, such as predicting between three choices or more. <i>Our task is to determine whether a person makes less or equal to $50k or more a year.</i></dd>
</dl>

<br>
Now, diving into our dataset by loading in our data. Let's get a glimpse of what we will be working with to make our prediction.

<figure>
<img src="/assets/img/import-data-Salary-Pred.PNG" alt="">
 <figcaption>Loading our dataset into Google Collab: 15 columns in total</figcaption>
</figure>
<br>

Making our way to now clean our data in order to explore and later perform some of that fancy modeling.I will keep the walkthroughs short and explain some of the behind the scenes to keep our post short and sweet. <br><i>Data cleaning process will be shown as follows</i>: Identifying duplicates, missing values and finally any inconsistencies in our values.

<figure>
<img src="/assets/img/duplicate-values.PNG" alt="">
 <figcaption>Identify and address any duplicate values</figcaption>
</figure>

We find our dataset has <mark>24 duplicates</mark> and make sure to drop them as they are unnecessary. These should carry no significant impact towards our modeling later on due to their small size in comparison to our data values. Moving on to any missing values which is important for more reason than one; for one, a dataset with a significant amount of missing values can cause for building a biased machine learning model with incorrect results. Another reason is that many machine learning models do not function properly with missing values. <br><br>There are many ways to deal with missing values depending on the problem to solve but that's a post for the future. Below we see that our dataset has no missing values.

<figure>
<img src="/assets/img/missing-values.PNG" alt="">
 <figcaption>Identify and address any missing values</figcaption>
</figure>

In the following two images we try to identify any inconsistencies within our values that may be present. For simplicity, we use the method <mark>.nunique()</mark> to return the number of unique values for each column in our data. We can also apply the <mark>.value_counts()</mark> method to return a list of the different values within a column like so: <br><br><i>dataFrame['columnName'].value_counts()</i><br><br>I remove spaces or any other irregularities within the values to employ a standardized set of values throughout our data. <i>(More on GitHub)</i>


<figure>
<img src="/assets/img/inconsistent-1.PNG" alt="">
 <figcaption>Identify Inconsistencies</figcaption>
</figure>
<figure>
<img src="/assets/img/inconsistent-2.PNG" alt="">
 <figcaption>Identify Inconsistencies</figcaption>
</figure>
<br>

With our data now clean, let's get to some visualizations that may help us understand it better. For some context, I have replaced all values of less than or equal to 50k to 0 and all values of greater than 50k to 1. As we consider these values to be categorical in nature, they must be one-hot encoded to prepare it for modeling and allow for better prediction results. 
<br><br>One hot encoding in this case works since there is no order of importance to the values, as we are not considering the values to be better than the other. An example of this would be a grading system from A to F, where order does matter. In that case, you would use ordinal encoding to achieve best results for your model.

<figure>
<img src="/assets/img/salary_breakdown.PNG" alt="">
 <figcaption>0 equals <=$50k and 1 equals >$50k</figcaption>
</figure>
<figure>
<img src="/assets/img/salary_gender.PNG" alt="">
 <figcaption>Salary breakdown between genders</figcaption>
</figure>
<figure>
<img src="/assets/img/top_5.PNG" alt="">
 <figcaption>Top 5 Occupations w/highest salaries</figcaption>
</figure>
<br>
There is definitely a few more parts to this project, which can be found on my GitHub page with full code and more visualizations to support the results presented at the end of this blog post.
<br><br>

### Final Results
The **KNN model** yielded better results in predicting whether a person makes over 50k a year.Due to it's classification report, we can see how it's precision score (81%) compares to the Random forest model (86%) of predicting a salary over 50K. The recall suggests that the Random Forest model only predicted the outcome correctly for 43% while KNN model reached 58%.<br>

<figure>
<img src="/assets/img/accuracy_score.PNG" alt="">
 <figcaption>Best model accuracy score: K-Nearest Neighbors</figcaption>
</figure>

The KNN model has the closest F1 score to 1, indicating better performance in predicting whether or not a person makes over 50k. For more on this project please visit my GitHub (found above in navigation) or click here for direct link to GitHub page - <a href="https://github.com/jeangarcia77/Salary-Prediction-Analysis">Salary Prediction Analysis</a>. 
  
<br>PowerPoint presentation here - <a href="https://docs.google.com/presentation/d/1DWoRXdvNVrWKYUw72BFdQDpyIZZYY6j70uRr9utBPJg/edit?usp=sharing">Salary Prediction Analysis PowerPoint</a>
