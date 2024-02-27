# hw-02

For any exercise where you’re writing code, insert a code chunk and make
sure to label the chunk. Use a short and informative label. For any
exercise where you’re creating a plot, make sure to label all axes,
legends, etc. and give it an informative title. For any exercise where
you’re including a description and/or interpretation, use full
sentences. Make a commit at least after finishing each exercise, or
better yet, more frequently. Push your work regularly to GitHub, and make sure 
all checks pass.

---

# Exploratory Data Analysis and Data Preprocessing Exercise

Welcome to your Exploratory Data Analysis and Data Preprocessing Exercise. This assignment is crucial for anyone diving into the field of data mining and data analysis. Your main objective in this exercise will be to conduct thorough exploratory data analysis (EDA) followed by meticulous data preprocessing on a given dataset. The dataset will be provided to you, and it will require a combination of Python and its powerful libraries, NumPy and Pandas, to uncover insights and prepare the data for any subsequent modeling tasks.

You will be expected to read in a dataset from the #[TidyTuesday 2023 datasets](https://github.com/rfordatascience/tidytuesday/tree/master/data/2023) for the purpose of exploratory data analysis and preprocessing. 

### Objective
Investigate the relationship between regional socioeconomic categories and the allocation of daily hours across countries. Analyze how the uncertainty in these allocations correlates with regional demographics and population sizes.

### Dataset

- [**Global Human Day**](https://github.com/rfordatascience/tidytuesday/tree/master/data/2023/2023-09-12)
- Use at least datasets `all_countries.csv` and `country_regions.csv`. 

The completion of this exercise is divided into two main parts:

- **Part 1: Exploratory Data Analysis**
- **Part 2: Data Preprocessing**

Before you start, ensure you have the latest versions of `Python`, `NumPy`, and `Pandas` installed on your system. Good documentation and commenting of your code are mandatory to make your code easy to understand.

---

## Part 1: Exploratory Data Analysis 

In this section, you will perform an exploratory data analysis on the provided dataset. You will identify patterns, detect outliers, and generate insights based on your findings.

### Task 1: Data Overview 
- Load the dataset into a Pandas DataFrame and display the first few rows.
- Provide a basic description of the dataset, including its shape, columns, and data types.

<details>
  <summary><h3><b>Hint</b></h3></summary>

- Use functions like `.head()`, `.shape`, `.columns`, and `.dtypes` to get an overview of your DataFrame.
- Remember that `.info()` can be used to get a concise summary of the DataFrame including the non-null count and type of each column.

</details>

### Task 2: Univariate Analysis 
- For numerical features, calculate descriptive statistics and create histograms.
- For categorical features, count unique values and create bar plots.

<details>
  <summary><h3><b>Hint</b></h3></summary>

- Use `.describe()` for a quick statistical summary of the numerical features.
- Utilize `matplotlib` or `seaborn` libraries to create histograms (`hist()` or `sns.histplot()`).
- For categorical data, `value_counts()` can help in understanding the distribution of classes, and you can plot the results using `bar()` or `sns.countplot()`.

</details>

### Task 3: Bivariate Analysis 
- Choose three pairs of numerical variables and create scatter plots to explore their relationships.
- Create boxplots for one numerical variable grouped by a categorical variable.

<details>
  <summary><h3><b>Hint</b></h3></summary>

- When creating scatter plots with `plt.scatter()` or `sns.scatterplot()`, it might be helpful to color points by a third categorical variable using the hue parameter in Seaborn.
- Use `sns.boxplot()` to create boxplots. Consider using the hue parameter if you have sub-categories within your categorical variable.

</details>

### Task 4: Missing Data and Outliers 
- Identify any missing values in the dataset.
- Detect outliers in the numerical features using an appropriate method (e.g., Z-score, IQR).

<details>
  <summary><h3><b>Hint</b></h3></summary>

- The `.isnull()` method chained with `.sum()` can help identify missing values.
- Consider using the `scipy.stats` module for Z-score computation or the `IQR` which is the range between the first and third quartile of your data distribution for outlier detection.

</details>

## Part 2: Data Preprocessing 

This section will focus on cleaning and preparing the dataset for modeling. You will correct any issues you found during the EDA phase.

### Task 1: Handling Missing Values 
- Choose appropriate methods to handle the missing data (e.g., imputation, removal).

<details>
  <summary><h3><b>Hint</b></h3></summary>

- Imputation methods could involve using `.fillna()` with measures like mean (`data.mean()`) for numerical columns and mode (`data.mode().iloc[0]`) for categorical columns.
- For removal, `.dropna()` is straightforward but consider the impact on your dataset size.

</details>

### Task 2: Dealing with Outliers 
- Treat or remove the outliers identified earlier based on your chosen methodology.

<details>
  <summary><h3><b>Hint</b></h3></summary>

- For outlier removal, you may use boolean indexing based on Z-scores or IQR to filter your data.
- If you don't want to remove outliers, consider transforming them using methods such as log transformation.

</details>

### Task 3: Feature Engineering 
- Create at least one new feature that could be useful for a data mining task.

<details>
  <summary><h3><b>Hint</b></h3></summary>

- Think about the domain knowledge related to your dataset that could suggest new features. For instance, if you have date-time information, extracting the day of the week could be useful.
- Also, combining features, if relevant, to create ratios or differences can often reveal useful insights.

</details>

### Task 4: Data Transformation 
- Standardize or normalize numerical features.
- Perform any additional transformations you deem necessary (e.g., encoding categorical variables, binning, etc.).

<details>
  <summary><h3><b>Hint</b></h3></summary>

- For scaling, `StandardScaler` or `MinMaxScaler` from `sklearn.preprocessing` can be applied to numerical features.
- For normalization, `np.log1p()` (log(1+x)) can help in managing skewed data.
- Use `pd.get_dummies()` or `LabelEncoder`/`OneHotEncoder` from `sklearn.preprocessing` for encoding categorical variables.

</details>

---

**Deliverables:**
- A Jupyter Notebook (with Quarto yaml configuration) containing all code and visualizations.
- A written report summarizing your findings from the EDA, the decisions you made during preprocessing, and the rationale behind your choices.

**Submission Guidelines:**
- Push your Jupyter Notebook to your GitHub repository.
- Ensure your commit messages are descriptive.
- Submit the link to your GitHub repository on the course submission page.

**Grading Rubric:**
Your work will be evaluated based on the following criteria:
- Correctness and completeness of the code.
- Quality and clarity of the visualizations and summary report.
- Proper use of comments and documentation in the code.
- Adherence to the submission guidelines.

**Points Distribution:**
Each task is allocated a specific number of points. Points will be awarded based on the completeness and correctness of the work submitted. Be sure to follow best practices in data analysis and provide interpretations for your findings and decisions during preprocessing.

Good luck, and may your insights be profound!
