
# Data Mining, Modeling and Biostatistics | Humber Polytechnic

A collection of R programming assignments, statistical computing exercises, and biomedical data analysis projects completed as part of the **Clinical Bioinformatics program at Humber Polytechnic**.

This repository documents my progression in learning R, from foundational programming and data wrangling to statistical analysis, data mining, and computational approaches used in biomedical research.

## Repository organization

## Repository organization

Each assignment has a dedicated folder containing its source document, rendered submission where available, assignment guide, and required input data. The practice problem follows the same pattern.

```text
Assignment_1_Breast_Cancer_Data_Wrangling/
Assignment_2_DataWrangling_in_R/
Assignment_3_BreastCancer_Visualization/
Assignment_4_Data_Modeling_DGE/
Practice_Problem_01/
```

Use the `.Rmd` files as editable report sources. Input datasets are stored beside the work that uses them; course modules, R session state, and unrelated files are not included.

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

---

## 📁 Repository Contents

This repository contains completed assignments, supporting datasets, and future statistical computing projects.

### Assignment 1: Introduction to R and Data Wrangling

- [Rendered assignment PDF](Assignment_1_Breast_Cancer_Data_Wrangling/Assignment01.pdf)
- [R Markdown source](Assignment_1_Breast_Cancer_Data_Wrangling/Assignment01.Rmd)
- [Breast cancer dataset](Assignment_1_Breast_Cancer_Data_Wrangling/breastCancer.csv)

The dataset is included in the assignment folder, and the source uses repository-relative paths.

---

## 🧬 Assignment 2: Data Wrangling

### Assignment Overview

This assignment focuses on using **R** and the **tidyverse** to perform vector operations, calculate descriptive statistics, and manipulate biological datasets.

The objective is to strengthen foundational data wrangling skills by working with numeric vectors and R's built-in `CO2` dataset, which contains measurements of carbon dioxide uptake in plants.

The assignment consists of two main parts:

1. Vector Operations and Statistical Calculations
2. CO2 Dataset Analysis and Data Wrangling

---

### Part A: Vector Operations and Statistical Calculations

#### Objective

Practice creating, indexing, transforming, and summarizing numeric vectors in R.

#### Tasks

**1. Create and compare vectors**

- Create a vector named `v` containing every integer from 0 through 30.
- Create a vector named `w` containing every third integer over the same range using `seq()`.
- Calculate the difference between the lengths of `v` and `w`.

**2. Perform vector indexing and statistical calculations**

- Create `v_square` by selecting elements at positions 3, 6, 7, 10, 15, 22, 23, 24, and 30 in `v` and squaring those values.
- Calculate the mean of the first five elements in `v_square`.
- Calculate the median of the first five elements in `v_square`.

**3. Apply logical comparisons**

- Create a Boolean vector named `v_bool` that identifies elements in `v` greater than 20.
- Determine how many values satisfy the condition using logical operations.

#### Programming Concepts

- Numeric vectors and sequence generation
- Vector length and indexing
- Arithmetic transformations
- Mean and median calculations
- Logical comparisons and Boolean values
- Conditional subsetting

---

### Part B: CO2 Dataset Analysis and Data Wrangling

#### Objective

Use R's built-in `CO2` dataset to summarize grouped observations, reorganize data, apply conditional transformations, and compare data manipulation approaches.

#### Dataset: CO2 Uptake in Grass Plants

**Source:** Built-in R dataset, accessible using `CO2` and documented with `?CO2`.

The dataset records carbon dioxide uptake measurements for grass plants under chilled and nonchilled conditions at different ambient CO2 concentrations.

| Variable | Description |
|----------|-------------|
| `Plant` | Identifier for each plant |
| `Type` | Plant origin (Quebec or Mississippi) |
| `Treatment` | Chilled or nonchilled treatment |
| `conc` | Ambient CO2 concentration (mL/L) |
| `uptake` | CO2 uptake rate (µmol/m²/s) |

#### Tasks

**1. Generate grouped summary statistics**

- Group the dataset by `Plant` and `Treatment`.
- Calculate the mean and standard deviation of CO2 uptake for each group.
- Count the number of observations in each group.
- Determine whether the dataset is balanced across the treatment groups.

**2. Arrange and interpret the summary table**

- Sort the grouped summary table from highest to lowest mean CO2 uptake.
- Identify the plant and treatment combinations with the highest and lowest mean uptake.
- Report the relevant values with appropriate units.

**3. Reshape the dataset into long format**

- Use `pivot_longer()` to combine `conc` and `uptake` into a column called `measurement`, with corresponding numeric values in a column called `values`.
- Save the reshaped dataset as `CO2_long`.
- Group the long-format data by `Plant`, `Treatment`, and `measurement`.
- Calculate group means and describe what is observed about the average ambient CO2 concentration.

**4. Filter observations and create a new variable**

- Starting from `CO2_long`, retain only observations with the `nonchilled` treatment and the `uptake` measurement.
- Create a new column called `values2` by multiplying `values` by 1.3.
- Save the result as `CO2_new`.

**5. Compare conditional data transformations**

- Create `CO2_new2` by applying `ifelse()` within `mutate()` to multiply the nonchilled uptake measurements by 1.3 while preserving other values.
- Compare `CO2_new` and `CO2_new2`, including their row counts.
- Explain how the three arguments of `ifelse()` determine which value is returned for each observation.
- Describe the difference between filtering rows before modification and conditionally modifying values while keeping all rows.

#### Data Wrangling Concepts

- Grouped data analysis with `group_by()` and `summarize()`
- Descriptive statistics using `mean()`, `sd()`, and `n()`
- Sorting observations with `arrange()` and `desc()`
- Reshaping data using `pivot_longer()`
- Filtering data with `filter()`
- Creating variables with `mutate()`
- Conditional transformations using `ifelse()`
- Interpreting experimental plant physiology data

---

## 🛠️ Technical Skills Developed

| Category | Skills |
|----------|--------|
| Programming Language | R |
| Development Environment | RStudio / R Markdown |
| Libraries | tidyverse, dplyr, tidyr |
| Data Structures | Numeric and Logical Vectors, Data Frames, Tibbles |
| Statistical Computing | Mean, Median, Standard Deviation, Counts |
| Data Manipulation | Indexing, Grouping, Sorting, Filtering, Reshaping |
| Conditional Logic | Logical Comparisons, `ifelse()` |
| Biological Applications | Plant CO2 Uptake Measurements |

---

## 🎯 Key Learning Outcomes

Through this assignment, I developed practical experience in:

1. Create and manipulate numeric and logical vectors in R.
2. Apply indexing and basic descriptive statistics to selected observations.
3. Summarize experimental measurements by relevant groups.
4. Recognize balanced versus unbalanced group sizes.
5. Convert data between wide and long formats.
6. Filter and transform biological measurements using tidyverse functions.
7. Distinguish between removing observations and conditionally modifying existing values.

---

---

## 📁 Assignment Files

- [Student guide](Assignment_2_DataWrangling_in_R/Assignment_2_Guide.pdf)
- [R Markdown source](Assignment_2_DataWrangling_in_R/Assignment_2_NM.Rmd)
- [Rendered assignment PDF](Assignment_2_DataWrangling_in_R/Assignment_2_NM.pdf)

The `CO2` dataset is built into R, so no separate download is required.

---

## 🧬 Assignment 3: Data Visualization

### Assignment Overview

This assignment applies data visualization principles to the Wisconsin Diagnostic Breast Cancer dataset. It examines how plot choice depends on variable type and uses plots to compare tumour measurements across benign and malignant diagnoses.

The assignment focuses on three main areas:

1. Selecting plots based on data types and analytical questions
2. Comparing tumour measurements across diagnosis groups
3. Reshaping data for faceted visualizations

---

### Part A: Plot Selection and Aesthetic Mapping

#### Objective

Explain how variable types and aesthetic mappings influence the choice and construction of a plot.

#### Tasks

1. Explain the difference between aesthetics set in `ggplot()` and aesthetics set within a geometry layer, and give an example of when layer-specific mapping is useful.
2. Distinguish a bar plot from a histogram and select the appropriate plot for continuous measurements such as student height.

#### Concepts Practiced

- Global and layer-specific aesthetic mappings
- Categorical and continuous variables
- Choosing a visualization to match the question
- Geoms and plot layers in `ggplot2`

---

### Part B: Visualizing Breast Cancer Measurements

#### Objective

Use the breast cancer dataset to compare distributions, examine relationships between measurements, and visualize multiple features by diagnosis.

#### Dataset: Wisconsin Diagnostic Breast Cancer

The dataset contains a diagnosis label and numerical measurements derived from digitized images of fine needle aspirates of breast masses. The analysis uses the diagnosis, mean radius, mean texture, mean smoothness, and mean compactness variables.

| Variable | Description |
|----------|-------------|
| `diagnosis` | Tumour classification: benign (`B`) or malignant (`M`) |
| `radius_mean` | Mean radius measurement of cell nuclei |
| `texture_mean` | Mean texture measurement of cell nuclei |
| `smoothness_mean` | Mean local variation in radius lengths |
| `compactness_mean` | Mean compactness measurement |

#### 1. Compare Mean Radius by Diagnosis

Diagnosis is categorical and `radius_mean` is continuous. A boxplot compares the distributions across diagnosis groups; jittered points show individual observations.

```r
ggplot(bCancer, aes(x = diagnosis, y = radius_mean)) +
  geom_boxplot() +
  geom_jitter(width = 0.1, alpha = 0.4) +
  scale_x_discrete(name = "Diagnosis",
                   labels = c("Benign", "Malignant")) +
  scale_y_continuous(name = "Mean radius") +
  ggtitle("Mean radius by diagnosis") +
  theme_classic()
```

#### 2. Examine Smoothness and Compactness

Both measurements are continuous, so a scatterplot displays their relationship with one point per observation.

```r
ggplot(bCancer, aes(x = smoothness_mean, y = compactness_mean)) +
  geom_point() +
  scale_x_continuous(name = "Mean smoothness") +
  scale_y_continuous(name = "Mean compactness") +
  ggtitle("Mean smoothness vs. mean compactness") +
  theme_classic()
```

#### 3. Compare Radius and Texture with Violin Plots

The two measurements are converted from wide to long format so they can be displayed in separate facets. The violin plots show each measurement's distribution by diagnosis.

```r
bCancer_long <- bCancer %>%
  pivot_longer(
    cols = c("radius_mean", "texture_mean"),
    names_to = "measurement",
    values_to = "value"
  )

ggplot(bCancer_long, aes(x = diagnosis, y = value, fill = diagnosis)) +
  geom_violin() +
  facet_wrap(~ measurement, scales = "free_y") +
  scale_x_discrete(labels = c("Benign", "Malignant")) +
  labs(title = "Mean radius and texture by diagnosis",
       x = "Diagnosis", y = "Mean measurement value",
       fill = "Diagnosis") +
  theme_classic()
```

#### 4. Plot Nine Mean Measurements

The nine specified mean measurements are reshaped into long format and plotted as histograms. Faceting with a free x-axis accommodates the different measurement ranges; colour indicates diagnosis.

```r
bCancer %>%
  pivot_longer(
    cols = radius_mean:symmetry_mean,
    names_to = "measurement",
    values_to = "value"
  ) %>%
  ggplot(aes(x = value, fill = diagnosis)) +
  geom_histogram(bins = 20, alpha = 0.6, position = "identity") +
  facet_wrap(~ measurement, scales = "free_x", ncol = 3) +
  labs(title = "Distributions of nine mean tumour measurements",
       x = "Mean measurement value", y = "Count",
       fill = "Diagnosis") +
  theme_classic()
```

#### Visualization Concepts

- Boxplots and jittered observations
- Scatterplots for two continuous variables
- Violin plots for grouped distributions
- Histograms for continuous-variable distributions
- Long-format data with `pivot_longer()`
- Faceting and free scales
- Labels, titles, colour, and fill aesthetics

---

## 🛠️ Technical Skills Developed

| Category | Skills |
|----------|--------|
| Programming Language | R |
| Development Environment | RStudio / R Markdown |
| Libraries | tidyverse, ggplot2, tidyr |
| Data Visualization | Boxplots, Scatterplots, Violin Plots, Histograms |
| Data Manipulation | Selecting and reshaping variables |
| Plot Design | Aesthetic mapping, facets, scales, labels, themes |
| Biomedical Data | Comparing tumour measurements by diagnosis |

---

## 🎯 Key Learning Outcomes

Through this assignment, I developed practical experience in:

1. Selecting plot types based on the variable types and question.
2. Distinguishing categorical bar plots from continuous-data histograms.
3. Comparing continuous measurements across diagnosis groups.
4. Visualizing relationships between two continuous variables.
5. Reshaping data to support multi-panel plots.
6. Formatting plots with labels, titles, colour, and appropriate scales.

---

## 📁 Assignment Files

- [R Markdown source](Assignment_3_BreastCancer_Visualization/NM_Assignment_3_BreastCancer_Visualization.Rmd)
- [Rendered assignment PDF](Assignment_3_BreastCancer_Visualization/NM_Assignment_3_BreastCancer_Visualization.pdf)
- [Breast cancer dataset](Assignment_3_BreastCancer_Visualization/breastCancer.csv)
- [Course-provided prompt/template](Assignment_3_BreastCancer_Visualization/3.Rmd) — included as instructions, separate from the completed report.

---

## 📊 Assignment 4: Data Modeling and Differential Gene Expression

### Assignment Overview

This assignment applies exploratory distribution checks, linear modeling, and differential expression analysis to breast cancer measurements and the Parathyroid experiment dataset.

The analysis is organized into two parts:

1. Breast cancer feature distributions and a linear model
2. Differential gene expression at 48 hours, controlling for patient

---

### Part A: Breast Cancer Data and Linear Modeling

#### Objective

Assess the distribution of `texture_mean`, choose a response transformation, fit a linear model using `area_mean`, and visualize the fitted relationship.

#### 1. Inspect the Distribution of `texture_mean`

Histograms and normal Q-Q plots are used to inspect the untransformed measurement and its log transformation. The untransformed values are mildly right-skewed; the log-transformed values appear more symmetric and closer to the Q-Q reference line.

```r
bCancer <- read.csv("breastCancer.csv", header = TRUE)

hist(bCancer$texture_mean,
     main = "Histogram of texture_mean",
     xlab = "texture_mean",
     col = "lightblue",
     border = "white")
qqnorm(bCancer$texture_mean)
qqline(bCancer$texture_mean, col = "red")

bCancer$texture_log <- log(bCancer$texture_mean)
hist(bCancer$texture_log,
     main = "Histogram of log(texture_mean)",
     xlab = "log(texture_mean)",
     col = "lightblue",
     border = "white")
qqnorm(bCancer$texture_log)
qqline(bCancer$texture_log, col = "red")
```

#### 2. Fit a Linear Model

The response is `log(texture_mean)` and the predictor is `area_mean`.

```r
texture_model <- lm(log(texture_mean) ~ area_mean, data = bCancer)
summary(texture_model)
```

The fitted model shows a statistically significant positive association between `area_mean` and log-transformed `texture_mean`. This is an association in the fitted model and does not establish causation.

#### 3. Visualize the Fitted Relationship

```r
model_intercept <- coef(texture_model)[1]
model_slope <- coef(texture_model)[2]

ggplot(bCancer, aes(x = area_mean, y = texture_log)) +
  geom_point() +
  geom_abline(intercept = model_intercept, slope = model_slope,
              color = "red", linewidth = 1) +
  xlab("area_mean") +
  ylab("log(texture_mean)") +
  theme_classic()
```

---

### Part B: Parathyroid Differential Gene Expression

#### Objective

Prepare the Parathyroid experiment count data, filter low-count genes, fit a treatment model while controlling for patient, and summarize the Control-versus-DPN comparison at 48 hours.

#### Dataset and Model

The count matrix and sample metadata are provided by the `parathyroidSE` R package. The design `~ patient + treatment` accounts for patient while estimating treatment differences. The analysis restricts the samples to the 48-hour time point.

```r
data("parathyroidGenesSE")

para <- assay(parathyroidGenesSE)
sample <- colData(parathyroidGenesSE)
colnames(para) <- colData(parathyroidGenesSE)$run

para_object <- DESeqDataSetFromMatrix(
  countData = para,
  colData = sample,
  design = ~ patient + treatment
)

para_object_subset <- para_object[, para_object$time == "48h"]
```

#### Analysis Tasks

1. Retain genes with nonzero counts in more than two sample columns.
2. Fit the filtered dataset using `DESeq()`.
3. Extract the Control-versus-DPN contrast and order results by adjusted p-value.
4. Report the five genes with the smallest non-missing adjusted p-values.
5. Count significant genes at an adjusted p-value threshold of 0.05 and interpret the direction of the contrast.
6. Plot normalized counts for the gene with the highest log2 fold change.
7. Create a volcano plot using the raw p-value cutoff of 0.05.

#### 1. Filter and Fit the Model

```r
para_object_filtered <- para_object_subset[
  rowSums(counts(para_object_subset) > 0) > 2,
]

diff_para <- DESeq(para_object_filtered)
```

The filter removes genes that have nonzero counts in two or fewer samples. It does not remove sample columns.

#### 2. Extract the DPN Contrast

```r
results_DPN <- results(
  diff_para,
  contrast = c("treatment", "Control", "DPN"),
  alpha = 0.05
)

results_DPN_sorted <- results_DPN[
  order(results_DPN$padj, na.last = NA),
]
top5_DPN <- head(
  results_DPN_sorted[, c("log2FoldChange", "pvalue", "padj")],
  5
)
```

For this contrast order, a positive log2 fold change indicates higher expression in Control than DPN; a negative value indicates higher expression in DPN. The adjusted p-value threshold used to count significant genes is 0.05.

#### 3. Visualize Results

The analysis uses `plotCounts()` to compare normalized counts for the gene with the highest log2 fold change and `EnhancedVolcano()` to display the DPN comparison using a raw p-value cutoff of 0.05.

#### Statistical and Data Analysis Concepts

- Histogram and normal Q-Q plot assessment
- Log transformation of a positive response variable
- Linear model fitting with `lm()`
- Model coefficients and fitted-line visualization
- Count matrices and sample metadata
- Low-count gene filtering
- Differential expression with `DESeq2`
- Treatment contrasts and log2 fold-change interpretation
- Adjusted and raw p-value thresholds
- Normalized count and volcano plot visualization

---

## 🛠️ Technical Skills Developed

| Category | Skills |
|----------|--------|
| Programming Language | R |
| Development Environment | RStudio / R Markdown |
| Packages | ggplot2, parathyroidSE, DESeq2, EnhancedVolcano |
| Distribution Assessment | Histograms, normal Q-Q plots, log transformation |
| Statistical Modeling | Linear regression, model coefficients, treatment contrasts |
| Gene Expression Analysis | Count filtering, DESeq2 model fitting, adjusted p-values |
| Visualization | Fitted-line plots, normalized count plots, volcano plots |

---

## 🎯 Key Learning Outcomes

Through this assignment, I developed practical experience in:

1. Assessing measurement distributions with histograms and Q-Q plots.
2. Applying and interpreting a log transformation.
3. Fitting and visualizing a linear model.
4. Preparing count data and sample metadata for differential expression analysis.
5. Filtering low-count genes and fitting a model that controls for patient.
6. Interpreting contrast direction, log2 fold changes, and p-value thresholds.
7. Visualizing normalized counts and differential expression results.

---

## 📁 Assignment Files

- [Student guide](Assignment_4_Data_Modeling_DGE/Assignment_4_Student_Guide.pdf)
- [R Markdown source](Assignment_4_Data_Modeling_DGE/Assignment_4_Data_Modeling_DGE.Rmd)
- [Rendered assignment PDF](Assignment_4_Data_Modeling_DGE/Assignment_4_Data_Modeling_DGE.pdf)
- [Breast cancer dataset](Assignment_4_Data_Modeling_DGE/breastCancer.csv)

---

## 🩺 Practice Problem 01: BMI and Glucose Regression

### Objective

Use BMI to model average glucose level in the included stroke dataset, then use the fitted line to make example predictions.

### Methodology

The analysis selects BMI and average glucose, converts BMI to numeric, and removes rows with missing values. It fits a linear model with average glucose as the response and BMI as the predictor, then calculates the slope and intercept for a prediction function.

The cleaned analysis contains 4,909 observations. The fitted relationship is positive and statistically significant, but the model's R-squared is 0.0308, so BMI alone explains only a small share of the observed glucose variation.

### Files

- [R Markdown source](Practice_Problem_01/Practice_Problem_01.Rmd)
- [Rendered report](Practice_Problem_01/Practice_Problem_01.pdf)
- [Dataset](Practice_Problem_01/healthcare-dataset-stroke-data.csv)

---

## 🚀 Future Development

As the course progresses, this repository will be updated with additional assignments and projects involving:

- Exploratory data analysis
- Statistical visualization
- Data mining techniques
- Statistical modeling
- Biomedical data interpretation
- Applied biostatistics

---

## 📖 References

Wolberg, W., Mangasarian, O., Street, N., & Street, W. (1995). *Breast Cancer Wisconsin (Diagnostic).* UCI Machine Learning Repository.

[Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

---

## 👨‍💻 Author

**Nafis Mohammad**  
Clinical Bioinformatics | Humber Polytechnic

**Research Interests:** Bioinformatics, Computational Biology, Cancer Genomics, and Biomedical Data Analysis

**Sept 2026 - May 2027**



