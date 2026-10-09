# HP_Data_Mining_Modeling_Biostatistics
All my projects and assignments with the R programming language from the Humber Polytechnic Data Mining, Modeling and Biostatistics course.


# Assignment 1: Introduction to R and Data Wrangling

**Course:** Data Mining, Modeling and Biostatistics  
**Author:** Nafis Mohammad  
**Date:** October 2026  
**Programming Language:** R

---

## 📌 Project Overview

This assignment focuses on fundamental R programming concepts and data wrangling techniques using the Wisconsin Diagnostic Breast Cancer dataset.

The objective is to develop foundational skills in data manipulation, statistical calculations, and working with biomedical datasets.

## 📊 Dataset

**Dataset:** Breast Cancer Wisconsin (Diagnostic)  
**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

The dataset contains diagnostic information derived from digitized images of breast mass cell nuclei.

Each observation is classified as:

- **M:** Malignant
- **B:** Benign

The dataset includes 30 numerical features based on 10 characteristics:

1. Radius
2. Texture
3. Perimeter
4. Area
5. Smoothness
6. Compactness
7. Concavity
8. Concave Points
9. Symmetry
10. Fractal Dimension

---

## 🎯 Assignment Objectives

### 1. R Programming Fundamentals

- Install and load R packages.
- Understand character, numeric, and logical data types.
- Explore automatic type coercion in R vectors.
- Create and manipulate data frames.

### 2. Functions and Statistical Calculations

- Calculate arithmetic means.
- Create custom functions.
- Apply conditional filtering to numerical vectors.
- Remove minimum and maximum values before calculating a mean.

### 3. Biomedical Data Wrangling

- Import CSV datasets into R.
- Access specific columns in data frames.
- Filter observations based on numerical conditions.
- Subset breast cancer diagnostic measurements.

---

## 💻 Code Examples

### Creating a Vector with Different Data Types

```r
x <- c(44, "Lion", TRUE)
x
```

**Result:** R converts all elements into character values because vectors must contain elements of the same atomic data type.

### Creating a Data Frame

```r
recent_fruits <- data.frame(
  colour = c("red", "yellow", "orange", "green", "black"),
  shape = c("round", "curved", "round", "oval", "pebbled"),
  taste = c(10, 10, 8, 6, 4),
  row.names = c("Apple", "Banana", "Orange", "Kiwi", "Blackberry")
)
```

### Calculating the Mean

```r
mean_taste <- mean(recent_fruits$taste)
mean_taste
```

**Result:** 7.6

### Creating a Custom Function

```r
middle_mean <- function(x) {
  x <- x[x != min(x) & x != max(x)]
  mean(x)
}

middle_mean(recent_fruits$taste)
```

**Result:** 7

### Importing and Filtering Breast Cancer Data

```r
breastCancer <- read.csv("breastCancer.csv")

large_tumour <- breastCancer[
  breastCancer$radius_mean < 20,
]
```

This operation selects observations where the mean cell nucleus radius is less than 20.

---

## 🛠️ Technologies and Skills

| Category | Skills |
|----------|--------|
| Programming | R |
| Development Environment | RStudio |
| Libraries | tidyverse, here |
| Data Manipulation | Data frames, vectors, subsetting |
| Statistical Computing | Mean, min, max, custom functions |
| Data Import | CSV files |
| Application | Biomedical data wrangling |

---

## 📚 Key Learning Outcomes

Through this assignment, I developed an understanding of:

- How R handles different data types and automatic type conversion.
- How to create and manipulate structured datasets.
- How to write reusable functions for statistical calculations.
- How to import and filter real-world biomedical data.
- How foundational data wrangling supports further statistical and bioinformatics analyses.

---

## 🔬 Relevance to Bioinformatics

This assignment provided foundational experience working with biomedical datasets.

Understanding how to import, structure, and manipulate biological measurements is essential for more advanced computational biology applications, including:

- Exploratory biomedical data analysis
- Statistical modeling
- Cancer data analysis
- Machine learning and classification

These techniques establish a foundation for future bioinformatics and computational biology projects.

---

## 📁 Repository Contents

- `README.md` — Project overview and documentation
- `Assignment01.pdf` — Completed assignment and results
- `Assignment01.Rmd` — R Markdown source code (if included)
- `breastCancer.csv` — Dataset (if included)

---

## 📖 References

UCI Machine Learning Repository.  
[Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)
I have also attached the .csv file in the Assignment 1 folder if you want to replicate it!

---

**Author:** Nafis Mohammad  
**October 2026**
