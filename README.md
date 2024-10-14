# 📝 Summer Summative ('Exam')

>_This README.md file shows the instructions for the individual project. Please see the **Main Work.qmd** file for the detailed project content and how I answered the following questions._

# 🗄️ Get the data

## What data will you be using?

You will be using two distinct datasets for this summative.

### Parts 1 and 2

Your dataset, for these parts, the CDC Diabetes Health Indicators dataset, comes from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators) where it was made public. This dataset was created for the purpose of better understanding relationship between lifestyle and diabetes in the US. It consists of demographics features, lab test results, and answers to survey questions for each patient. The target variable (`Diabetes_012`) in this dataset encodes whether a patient has diabetes (value 1), is pre-diabetic (value 2), or is healthy (value 0).

**Preparation**

1. Download the data by clicking on the button below.

<a href="cdc_diabetes.csv" style="margin-left:2em;" download>
    <button class="button-61">Download CDC Diabetes Health Indicators dataset (csv file)</button>
</a>

### Part 3

In this part, you're again using a dataset made publicly available on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/462/drug+review+dataset+drugs+com). This time, it's a dataset that provides patient reviews on specific drugs along with related conditions and a 10 star patient rating reflecting overall patient satisfaction. The data was obtained by crawling online pharmaceutical review sites. Based on an initial associated publication (see UCI website), the data was split in into training (75%) and test (25%) sets and stored into two distinct .tsv (tab-separated-values) files, respectively (both compressed in a zip archive).

**Preparation**

Click on the button below to download the dataset:

<a href="drug_review_dataset.zip" style="margin-left:2em;" download>
    <button class="button-61">Download Drug reviews dataset (zip file)</button>
</a>


# 📋 Your Tasks

**What do we actually want from you?**

## Context

While we provide data, we will not specify the insights we seek in some questions. Instead, we will task you with proposing your approach to the data/question. This mirrors real-world scenarios in data science and academic research, where you are often given a dataset and asked to derive insights or address a problem.

💡 **Remember**: if you decide to write R code, please ensure your code confirms, reinforces, or complements your answers and that it aligns with the style of code we practiced throughout the course. Adding code just for the sake of it will not help you get a higher grade.

## Part 1: About Supervised Learning... (50 marks) 🤔

**All the questions in this part relate to the CDC Diabetes Health Indicators Dataset**

### Question 1 (15 marks)

A data scientist is tasked with coming up with a model that predicts the target variable `Diabetes_012` (i.e classifies people as healthy, pre-diabetic or diabetic).

Below is the code that the data scientist wrote as well as a figure representing the model the data scientist came up with

<details>
<summary>Code</summary>
    
```r
library(tidymodels)
library(rpart.plot)
library(dplyr)
library(readr)
library(recipes)

# Load the dataset
url <- "cdc_diabetes.csv"
diabetes_data <- read_csv(url)

# Display the first few rows of the dataset
head(diabetes_data)

diabetes_data <- diabetes_data %>%
  mutate(across(where(is.character), as.factor))

diabetes_data$Diabetes_012 <- as.factor(diabetes_data$Diabetes_012)

set.seed(42)

# Split the data into training (70%) and testing (30%) sets
data_split <- initial_split(diabetes_data, prop = 0.7)
train_data <- training(data_split)
test_data <- testing(data_split)

# Define a decision tree model 

tree_rec <-
  recipe(Diabetes_012 ~ .,
         data = train_data)

tree_spec <- decision_tree(cost_complexity = 0, mode="classification") %>%
  set_engine("rpart") 

# Define the workflow
tree_workflow <- workflow() %>%
  add_recipe(tree_rec) %>% 
  add_model(tree_spec) 

# Fit the model on the training data
tree_model <- 
  tree_workflow %>% 
  fit(data = train_data)

# Visualize the tree
tree_fit <- tree_model %>% extract_fit_engine()
rpart.plot(tree_fit,roundint=FALSE)
```
</details>

![](tree_plot.svg)

> Q1 : What do you see? What choices do you think lay behind the data scientist's modeling? Do you think this is a good model? And if not, why not?

### Question 2 (15 marks)

> Q2: What would you do differently from what the data scientist chose to do? How would you evaluate your model? Why?

### Question 3 (20 marks) 

Consider this scenario. A (random and varying) portion of the target labels is now poisoned i.e a portion of the labels is now corrupted and incorrect (usually due to an attack).

You can generate the data with poisoned labels with the code below.

<details>
<summary>Code</summary>
    
```r
# Load necessary libraries
library(tidymodels)
library(tidyverse)

# Load the CDC Diabetes Health Indicators dataset
# Replace this with the actual path to your dataset
diabetes_data <- read_csv("cdc_diabetes.csv")

# Function to poison a percentage of labels in the target column
poison_labels <- function(data, target_column, poison_percentage) {
  set.seed(42)
  n <- nrow(data)
  num_to_poison <- round(n * poison_percentage / 100)
  
  # Ensure the target column is a factor
  data[[target_column]] <- as.factor(data[[target_column]])
  
  # Randomly select indices to poison
  poison_indices <- sample(seq_len(n), size = num_to_poison, replace = FALSE)
  
  # Possible class labels
  possible_labels <- levels(data[[target_column]])
  
  # Poison the selected labels
  for (i in poison_indices) {
    current_label <- data[[target_column]][i]
    new_label <- sample(possible_labels[possible_labels != current_label], 1)
    data[[target_column]][i] <- new_label
  }
  
  return(data)
}

# Poison 10% of the Diabetes_012 labels in the dataset
# Change the last parameter to change the proportion of labels poisoned
poisoned_data <- poison_labels(diabetes_data, "Diabetes_012", 10)

# Inspect the first few rows of the poisoned data
head(poisoned_data)
```
</details>

> Q3: How would you approach such a situation? And would you still manage to make predictions about the health status of a person (i.e healthy, pre-diabetic or diabetic)?


## Part 2: Exploring diabetic/prediabetic patients characteristics (20 marks) 🩻

**In this part too, you should rely on the CDC Diabetes Health Indicators dataset for reference.**

Suppose we have a few candidate drugs/treatments we want to trial. We first want to understand whether there are particular patterns/characteristics in our patient groups that might induce similar responses to the drugs/treatments.

How would you approach this task?

## Part 3: Pharmaceutical reviews (30 marks) ⭐

**Your dataset, in this part, is the drug reviews dataset**

Question 4 (30 marks):

> Q4: Propose **one compelling research question** that one could investigate with this dataset. How would you start answering that question? The choice of methods to use in this research is entirely yours: your only constraint is that the reviews data has to be used in some shape or form in your research (and of course, the topics of the original publication paper that introduced this dataset are off limits 😉).

---

Finally:

Well done on getting this far!🎉

> Q: How do you plan on rewarding yourself (as you should!) after completing this exam?



