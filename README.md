# Laptop-Pricing
The dataset used is a modified subset that maps the price of laptops with different attributes.  The dataset is a filtered and modified version of the Laptop Price Prediction using specifications dataset, available under the Database Contents License (DbCL) v1.0 on the Kaggle website.

# Data Processing and Preprocessing
## Objectives
- Import a dataset from a CSV file to a Pandas dataframe
- Develop some basic insights about the dataset
- Handle missing data in different ways
- Correct the data type of different data values as per requirement
- Standardize and normalize the appropriate data attributes
- Visualize the data as grouped bar graph using Binning
- Converting a categorical data into numerical indicator variables

## Setup
- pandas for managing the data.
- numpy for mathematical operations.
- matplotlib for additional plotting tools.
- scipy for statistical operations
- seaborn for visualizing the data

## Parameters
The parameters used in the dataset are:
- Manufacturer: The company that manufactured the laptop
- Category: The category to which the laptop belongs: This parameter is mapped to numerical values in the following way:
  | Category    | Assigned Value |
  |-------------|----------------|
  | Gaming      | 1              |
  | Netbook     | 2              |
  | Notebook    | 3              |
  | Ultrabook   | 4              |
  | Workstation | 5              |
  
- GPU:The manufacturer of the GPU. This parameter is mapped to numerical values in the following way:
  | GPU   | Assigned Value |
  |-------|----------------|
  | AMD   | 1              |
  | Intel | 2              |
  | NVidia| 3              |
  
- OS: The operating system type (Windows or Linux): This parameter is mapped to numerical values in the following way:
  | OS      | Assigned Value |
  |---------|----------------|
  | Windows | 1              |
  | Linux   | 2              |

- CPU_core:The type of processor used in the laptop: This parameter is mapped to numerical values in the following way:
  | CPU Core           | Assigned Value |
  |--------------------|----------------|
  | Intel Pentium i3   | 3              |
  | Intel Pentium i5   | 5              |
  | Intel Pentium i7   | 7              |

- Screen_Size_cm : The size of the laptop screen is recorded in cm.
- CPU_frequency: The frequency at which the CPU operates, in GHz.
- RAM_GB : The size of the RAM of the system in GB.
- Storage_GB_SSD :The size of the SSD storage in GB is installed in the laptop.
- Weight_kg: The weight of the laptop is in kgs.
- Price :The price of the laptop is in USD.

### Task 1: Import the dataset using the url
- import libraries
- Load the dataset to a pandas dataframe named 'df'
- Add headers to the dataframe
- Replace '?' with 'NaN'¶
- Print the data types of the dataframe columns
- Print the statistical description of the dataset, including that of 'object' data types.
- Print the summary information of the dataset.

### Task 2: Evaluate the dataset for missing data
Missing data was last converted from '?' to numpy.NaN. Pandas uses NaN and Null values interchangeably. This means, you can just identify the entries having Null values

### Task 3: Replace with mean and mode
- Replace null values in Weight_kg with the mean of weight
- Replace null values in Screen_size_cm  with the most frequent value

### Task 4: Fixing the data types
Both "Weight_kg" and "Screen_Size_cm" are seen to have the data type "Object", while both of them should be having a data type of "float".
So, both of them are converted to float data type

### Task 5: Data Standardization
The value of Screen_size usually has a standard unit of inches. Similarly, weight of the laptop is needed to be in pounds. Use the below mentioned units of conversion and write a code to modify the columns of the dataframe accordingly. Update their names as well.
1 inch = 2.54 cm
1 kg   = 2.205 pounds

### Task 6: Data Normalization
Often it is required to normalize a continuous data attribute. Write a code to normalize the "CPU_frequency" attribute with respect to the maximum value available in the dataset.

### Task 7: Binning
Binning is a process of creating a categorical attribute which splits the values of a continuous data into a specified number of groups. In this case, write a code to create 3 bins for the attribute "Price". These bins would be named "Low", "Medium" and "High". The new attribute will be named "Price-binned".

### Task 8: Indicator variables
Convert the "Screen" attribute of the dataset into 2 indicator variables, "Screen-IPS_panel" and "Screen-Full_HD". Then drop the "Screen" attribute from the dataset.

# Exploratory Data Analysis
## Objectives
- Visualize individual feature patterns
- Run descriptive statistical analysis on the dataset
- Use groups and pivot tables to find the effect of categorical variables on price
- Use Pearson Correlation to measure the interdependence between variables

### Task1: Visualize individual feature patterns
- Continuous valued features
  Generate regression plots for each of the parameters "CPU_frequency", "Screen_Size_inch" and "Weight_pounds" against "Price". Also, print the value of correlation of each feature with   "Price".
- Categorical features
  Generate Box plots for the different feature that hold categorical values. These features would be "Category", "GPU", "OS", "CPU_core", "RAM_GB", "Storage_GB_SSD"

### Task 2: Descriptive Statistical Analysis
Generate the statistical description of all the features being used in the data set. Include "object" data types as well.

### Task 3: GroupBy and Pivot Tables
Group the parameters "GPU", "CPU_core" and "Price" to make a pivot table and visualize this connection using the pcolor plot.

### Task 4: Pearson Correlation and p-values
Use the scipy.stats.pearsonr() function to evaluate the Pearson Coefficient and the p-values for each parameter tested in task 3. This will help you determine the parameters most likely to have a strong effect on the price of the laptops.
