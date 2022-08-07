---
layout: post
title:  Salary Prediction Analysis
date:   2022-08-03
description: This is a post description for meta purposes. This is also the excerpt of the article that shows up on the index/home page. Change this in the post YAML.
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

We find our dataset has 24 duplicates and make sure to drop them as they are unnecessary. These should carry no significant impact towards our modeling later on due to their small size in comparison to our data values. Moving on to any missing values which is important for more reason than one; for one, a dataset with a significant amount of missing values can cause for building a biased machine learning model with incorrect results. Another reason is that many machine learning models do not function properly with missing values. There are many ways to deal with missing values depending on the problem to solve but that's a post for the future. Below we see that our dataset has no missing values.

<figure>
<img src="/assets/img/missing-values.PNG" alt="">
 <figcaption>Identify and address any missing values</figcaption>
</figure>

In the following two images we try to identify any inconsistencies within our values that may be present. For simplicity, we use the method <mark>.nunique()</mark> to return the number of unique values for each column in our data. We can also apply the <mark>.value_counts()</mark> method to return a list of the different values within a column like so: <br><i>dataFrame['columnName'].value_counts()</i>.<br>I remove spaces or any other irregularities within the values to employ a standardized set of values throughout our data. 


<figure>
<img src="/assets/img/inconsistent-1.PNG" alt="">
 <figcaption>Identify Inconsistencies</figcaption>
</figure>
<br>
<figure>
<img src="/assets/img/inconsistent-2.PNG" alt="">
 <figcaption>Identify Inconsistencies</figcaption>
</figure>


Curabitur blandit tempus porttitor. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Curabitur blandit tempus porttitor. Nullam quis risus eget urna mollis ornare vel eu leo. Maecenas faucibus mollis interdum. Nullam id dolor id nibh ultricies vehicula ut id elit.
