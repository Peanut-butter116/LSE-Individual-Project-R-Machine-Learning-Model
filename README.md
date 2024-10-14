[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/jyrbdRQh)
# 📝 Summer Summative ('Exam')

💡 **NOTE:** This time as well, you are not _asked_ to write code as part of the assignment. If you choose to do so, please ensure your code confirms, reinforces, or complements your answers. Adding code just for the sake of it will not help you get a higher grade. 


⏲️ **Due Date**: Friday, May 31st 2024 at 11:59:59 am (**midday** London time)  

If you update your files on GitHub after this date without an authorised extension, you will receive a [late submission penalty](https://info.lse.ac.uk/current-students/services/assessment-and-results/exams/exam-discipline-and-academic-misconduct).

Did you have an extenuating circumstance and need an extension? Send an e-mail to 📧 [Kevin](mailto:DSI.ug@lse.ac.uk?subject=DS202A%20-%20Summer%20Summative%20Extension)

⚖️ **Assignment Weight**:

This assignment is worth 40% of your final grade in this course.

<button style="background-color:'#c63c4a';border:none;color:#fff;">

40%

</button>


## Do you know your CANDIDATE NUMBER? You will need it.

> _"Your candidate number is a unique five digit number that ensures that your work is marked anonymously. It is different to your student number and will change every year. **Candidate numbers can be accessed using LSE for You.**"_ 

Source: [LSE](https://www.lse.ac.uk/accounting/study/New-Arrival/Exams-and-Assessments)


# 📝 Instructions

👉 Read it carefully, as some details might change from one assignment to another.

1. Go to our Slack workspace's `#announcements` channel to find a GitHub Classroom link entitled 📝 **Summer Summative ('Exam')**. Do not share this link with anyone outside this course!

2. Click on the link, sign in to GitHub, and then click on the green `Accept this assignment` button.

3. You will be redirected to a new private repository created just for you. The repository will be named `ds202w-2024-exam-yourusername`, where `yourusername` is your GitHub username. The repository will be private and will contain a `README.md` file with a copy of these instructions.

4. Recall what is your LSE CANDIDATE NUMBER. You will need it in the next step.

5. Create a `<CANDIDATE_NUMBER>.qmd` file with your answers, replacing the text `<CANDIDATE_NUMBER>` with your actual LSE number. 

    For example, if your candidate number is `12345`, then your file should be named `12345.qmd`.

6. Then, replace whatever is between the `---` lines at the top of your newly created `.qmd` file with the following:

    ```yaml
    ---
    title: "DS202W - Summer Summative ('Exam')"
    author: <CANDIDATE_NUMBER>
    output: html
    self-contained: true
    ---
    ```

    Once again, replace the text `<CANDIDATE_NUMBER>` with your actual LSE CANDIDATE NUMBER. For example, if your candidate number is `12345`, then your `.qmd` file should start with:

    ```yaml
    ---
    title: "DS202W - DS202W - Summer Summative ('Exam')"
    author: 12345
    output: html
    self-contained: true
    ---
    ```

7. Fill out the `.qmd` file with your answers. **This time, you are not _required_ to write code. Still, you should provide a nicely formatted notebook.**

    - Use headers and code chunks to keep your work organised. This will make it easier for us to grade your work. Learn more about the basics of **markdown formatting** [here](https://quarto.org/docs/authoring/markdown-basics.html). 

8. Once done, click on the `Render` button at the top of the `.qmd` file. This will create an `.html` file with the same name as your `.qmd` file. For example, if your `.qmd` file is named `12345.qmd`, then the `.html` file will be named `12345.html`. 

    - **If you added any code,** ensure your `.qmd` code is reproducible. If we were to restart R and RStudio and run your notebook, it should run without errors, and we should get the same results as you did.

    - If you choose to add code, please ensure your code confirms, reinforces, or complements your answers. Adding code just for the sake of it will not help you get a higher grade.

9. Push both files to your GitHub repository. You can push your changes as many times as you want before the deadline. We will only grade the last version of your assignment. Not sure how to use Git on your computer? You can always add the files via the GitHub web interface.

10. Read the section **How to get help and collaborate with others** at the end of this document.

## "What do I submit?"

You will submit two files:

- A Quarto markdown file with the following naming convention: `<CANDIDATE_NUMBER>.qmd`, where `<CANDIDATE_NUMBER>` is your candidate number. For example, if your candidate number is `12345`, then your file should be named `12345.qmd`.

- An HTML file render of the Quarto markdown file.

You don't need to click to submit anything. Your assignment will be automatically submitted when you `commit` **AND** `push` your changes to GitHub. You can push your changes as many times as you want before the deadline. We will only grade the last version of your assignment. Not sure how to use Git on your computer? You can always add the files via the GitHub web interface.

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


# How to get help and collaborate with others


## 🙋 What if I am confused?

- This is a **test**. Certain questions are intentionally open-ended and somewhat vague. Part of the assignment involves deciphering what we want from you.

- We will assess your ability to identify which of the concepts you learned in class are relevant to a given problem at hand and how to apply them to solve it. Strive to achieve that neat balance of **conciseness** and **completeness**.

- However, if you feel that a question is **too** ambiguous, please send an e-mail or a private Slack message to [Ghita](mailto:G.Berrada@lse.ac.uk). If we deam your question valid, we will post a clarification on the public Slack channel. If you don't get a response, assume that the question is not ambiguous and you should proceed with your best judgement.

## 👯 Can I get help from others?

⚠️ **For this assignment, we expect you to work independently and refrain from discussing it with your peers.** 

⚠️ This task presents a significant challenge, and your grade will greatly benefit from your personal creativity and originality. It is crucial that your responses are distinct and unique compared to your classmates' work.

   - Nonetheless, you are allowed to use the internet, refer to course materials, and even Generative AI tools when working on your answers. Again, try to aim for originality, do not let these resources dictate your answers.

   - Consult the 🤖 [Our Generative AI policy](https://lse-dsi.github.io/DS202/2023/winter-term/generative-ai.html) to see examples of how to report the use of Generative AI tools in your work.

## 🤖 Using AI help?

You can use Generative AI tools such as ChatGPT when doing this research and search online for help. If you use it, however minimal use you made, you are asked to report the AI tool you used and add an extra section to your notebook to explain how much you used it.

Note that while these tools can be helpful, they tend to generate responses that sound convincing but are not necessarily correct. Another problem is that they tend to create formulaic and repetitive responses, thus limiting your chances of getting a high mark. When it comes to coding, these tools tend to generate code that is not very efficient or old and does not follow the principles we teach in this course.

To see examples of how to report the use of AI tools, see 🤖 [Our Generative AI policy](https://lse-dsi.github.io/DS202/2023/winter-term/generative-ai.html).



