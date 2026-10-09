
# Data Mining, Modeling and Biostatistics | Humber Polytechnic

A collection of R programming assignments, statistical computing exercises, and biomedical data analysis projects completed as part of the **Clinical Bioinformatics program at Humber Polytechnic**.

This repository documents my progression in learning R, from foundational programming and data wrangling to statistical analysis, data mining, and computational approaches used in biomedical research.

As the course progresses, this repository will be updated with additional assignments and projects.

---

## 📚 Course Overview

**Institution:** Humber Polytechnic  
**Program:** Clinical Bioinformatics (Ontario Graduate Certificate)  
**Course:** Data Mining, Modeling and Biostatistics  
**Programming Language:** R  
**Development Environment:** RStudio

### Learning Objectives

- Develop foundational R programming skills.
- Understand data types, vectors, and data frames.
- Perform statistical calculations using R.
- Create reusable functions for data processing.
- Import, organize, and manipulate biomedical datasets.
- Apply conditional filtering and data subsetting.
- Build a foundation for statistical modeling and data mining in bioinformatics.

---

## 🧬 Assignment 1: Introduction to R and Data Wrangling

### Assignment Overview

This assignment introduces fundamental R programming concepts and data wrangling techniques through introductory programming exercises and the analysis of the Wisconsin Diagnostic Breast Cancer dataset.

The primary objective is to develop practical experience working with R data structures, statistical functions, and biomedical datasets.

The assignment focuses on three main areas:

1. R Programming Fundamentals
2. Functions and Statistical Calculations
3. Biomedical Data Wrangling

---

### Part A: R Programming Fundamentals

#### Objective

Develop familiarity with R programming syntax, data types, vectors, and data frames.

#### Tasks

- Install and load R packages.
- Create vectors containing different data types.
- Observe automatic type coercion.
- Construct data frames using multiple variables.
- Access and manipulate values within structured datasets.

#### Example: Data Type Coercion

```r
x <- c(44, "Lion", TRUE)
x
```

**Explanation:**

R vectors must contain elements of the same atomic data type.

When numeric, character, and logical values are combined, R automatically converts the elements into a common compatible type.

In this example, all values are converted to character strings.

#### Example: Creating a Data Frame

```r
recent_fruits <- data.frame(
  colour = c("red", "yellow", "orange", "green", "black"),
  shape = c("round", "curved", "round", "oval", "pebbled"),
  taste = c(10, 10, 8, 6, 4),
  row.names = c(
    "Apple",
    "Banana",
    "Orange",
    "Kiwi",
    "Blackberry"
  )
)
```

This exercise demonstrates how multiple variables can be combined into a structured data frame, where rows represent observations and columns represent attributes.

#### Programming Concepts

- Variable assignment
- Atomic vectors
- Data type coercion
- Character, numeric, and logical values
- Data frame creation
- Row names and column organization

---

### Part B: Functions and Statistical Calculations

#### Objective

Apply basic statistical operations and develop custom functions to manipulate numerical data.

#### 1. Calculating the Arithmetic Mean

```r
mean_taste <- mean(recent_fruits$taste)
mean_taste
```

**Result:** `7.6`

The `mean()` function calculates the arithmetic average of the numerical values stored in the `taste` column.

#### 2. Creating a Custom Function

```r
middle_mean <- function(x) {
  x <- x[x != min(x) & x != max(x)]
  mean(x)
}

middle_mean(recent_fruits$taste)
```

**Result:** `7`

The custom `middle_mean()` function:

1. Accepts a numerical vector.
2. Identifies the minimum and maximum values.
3. Excludes values equal to the minimum or maximum.
4. Calculates the mean of the remaining observations.

This exercise demonstrates how conditional filtering can be incorporated into reusable functions.

#### Programming Concepts

- Built-in statistical functions
- Custom function definitions
- Function arguments and return values
- Logical comparisons
- Conditional vector subsetting
- Arithmetic mean calculations

---

### Part C: Biomedical Data Wrangling

#### Objective

Import and manipulate a real-world biomedical dataset using R.

#### Dataset: Breast Cancer Wisconsin (Diagnostic)

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

The dataset contains measurements derived from digitized images of fine needle aspirates (FNA) of breast masses.

These measurements describe characteristics of cell nuclei and are associated with a diagnostic classification.

#### Diagnostic Categories

| Classification | Description |
|----------------|-------------|
| M | Malignant |
| B | Benign |

#### Dataset Features

The dataset contains 30 numerical features derived from 10 characteristics of cell nuclei.

| Feature | Description |
|---------|-------------|
| Radius | Mean distance from the center to points on the perimeter |
| Texture | Standard deviation of gray-scale values |
| Perimeter | Measurement of the nucleus boundary |
| Area | Area of the nucleus |
| Smoothness | Local variation in radius lengths |
| Compactness | Relationship between perimeter and area |
| Concavity | Severity of concave portions of the contour |
| Concave Points | Number of concave portions of the contour |
| Symmetry | Symmetry of the nucleus |
| Fractal Dimension | Measure of contour complexity |

Each characteristic is represented by mean, standard error, and worst-value measurements, resulting in 30 numerical features.

#### 1. Importing the Dataset

```r
breastCancer <- read.csv("breastCancer.csv")
```

The `read.csv()` function imports the dataset into R as a data frame for further manipulation.

#### 2. Filtering Observations

```r
large_tumour <- breastCancer[
  breastCancer$radius_mean < 20,
]
```

This operation creates a subset of observations where the mean cell nucleus radius is less than 20.

Although the variable is named `large_tumour`, the filtering condition specifically selects observations with `radius_mean < 20`.

#### Data Wrangling Concepts

- CSV file import
- Data frame manipulation
- Column selection
- Conditional filtering
- Logical indexing
- Observation subsetting
- Biomedical feature interpretation

---

## 🛠️ Technical Skills Developed

| Category | Skills |
|----------|--------|
| Programming Language | R |
| Development Environment | RStudio |
| R Packages | tidyverse, here |
| Data Structures | Vectors, Data Frames |
| Data Types | Numeric, Character, Logical |
| Statistical Computing | Mean, Minimum, Maximum |
| Functions | Custom Functions, Arguments |
| Data Wrangling | Filtering, Subsetting, CSV Import |
| Biomedical Applications | Breast Cancer Diagnostic Data |

---

## 🎯 Key Learning Outcomes

Through this assignment, I developed practical experience in:

1. Understanding how R handles different data types and automatic type coercion.
2. Creating and manipulating structured datasets using vectors and data frames.
3. Performing statistical calculations using built-in R functions.
4. Developing custom functions for numerical data processing.
5. Importing and filtering biomedical datasets.
6. Interpreting biological measurements within a computational analysis environment.

These skills provide a foundation for more advanced statistical and computational approaches in bioinformatics.

---

## 🔬 Relevance to Bioinformatics

Data wrangling and statistical computing are essential components of modern bioinformatics research.

Biological datasets often contain large numbers of quantitative measurements that must be organized, filtered, and analyzed before meaningful conclusions can be drawn.

The skills introduced in this assignment are relevant to:

- Biomedical data preprocessing
- Exploratory data analysis
- Cancer genomics and diagnostic research
- Statistical modeling
- Machine learning classification
- Biological feature analysis
- Reproducible computational research

Working with breast cancer diagnostic measurements provided introductory experience in handling structured biomedical data and understanding how quantitative cellular characteristics can be represented computationally.

Although this assignment focuses on foundational R programming and data manipulation rather than predictive modeling, these techniques are important prerequisites for more advanced analyses.

---

## 📁 Repository Contents

This repository contains completed assignments, supporting datasets, and future statistical computing projects.

### Assignment 1: Introduction to R and Data Wrangling

- `Assignment01.pdf` — Completed assignment and results
- `Assignment01.Rmd` — R Markdown source code, if available
- `breastCancer.csv` — Breast cancer diagnostic dataset

**Reproducibility:**

The `breastCancer.csv` dataset is included in the Assignment 1 folder to allow others to reproduce the data import and filtering exercises.

To reproduce the analysis:

1. Download or clone this repository.
2. Open the assignment in RStudio.
3. Ensure the dataset is accessible from the working directory.
4. Run the R code included in the assignment.

---

## 🚀 Future Development

As the course progresses, this repository will be updated with additional assignments and projects involving:

- Exploratory data analysis
- Statistical visualization
- Data mining techniques
- Statistical modeling
- Biomedical data interpretation
- Applied biostatistics

These future exercises will build upon the foundational R programming and data wrangling concepts introduced in Assignment 1.

---

## 📖 References

Wolberg, W., Mangasarian, O., Street, N., & Street, W. (1995). *Breast Cancer Wisconsin (Diagnostic).* UCI Machine Learning Repository.

[Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

---

## 👨‍💻 Author

**Nafis Mohammad**  
Clinical Bioinformatics | Humber Polytechnic

**Research Interests:** Bioinformatics, Computational Biology, Cancer Genomics, and Biomedical Data Analysis

**October 2026**

