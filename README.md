# Student Depression Prediction: A Comparison between XGBoost and Random Forest

## Description 

This project aims to identify whether students show a tendency toward depression based on lifestyle and demographic factors. By comparing two machine learning models (XGBoost and Random Forest) this study explores how these algorithms can detect patterns that may indicate early stages of depression, ultimately helping students who are experiencing depression to seek mental health support.

## Dataset 

The dataset used in this research was obtained from Kaggle: [Student Depression Dataset](https://www.kaggle.com/datasets/adilshamim8/student-depression-dataset)

- **Total Records**: 27,900
- **Attributes**: 18
- **Format**: Tabular data

## Objectives 

1. Data Cleaning and Preprocessing  
2. Exploratory Data Analysis (EDA)  
3. Feature Selection and Data Splitting  
4. Model Building (Random Forest and XGBoost)  
5. Model Evaluation and Comparison  
6. Insights and Interpretation

## Tools & Libraries 

Python (Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib, XGBoost)

## Data Preprocessing 

### 1. Missing Values and Duplicate Detection
I performed checks for null values and duplicates. No duplicate values were found, but several entries contained question marks ("?"). Fields containing question marks were replaced with NaN and removed from the dataset.

### 2. Data Mapping and Type Conversion 
Many features were in categorical format, so I performed mapping to convert the following attributes into numeric values for easier model processing:
- Gender
- Dietary Habits
- Sleep Duration
- Have you ever had suicidal thoughts?
- Financial Stress
- Family History of Mental Illness

### 3. Feature Selection
I removed attributes with object data types as they cannot be processed directly by the models. After cleaning, the dataset was reduced to **11 attributes**.

### 4. Train-Test Split
The data was split into **80% training** and **20% testing** sets for model development and evaluation.

## Exploratory Data Analysis (EDA)
Through this analysis, I was able to obtain several insights from the dataset, as summarized below : 
### 1. Student Depression Distribution 

![Student Depression Distribution](image-1.png)

### 2. Academic Pressure vs. Depression
![Academic Pressure vs Depression](image-2.png)

Students with depression have higher academic pressure compared to those without depression. The median and data distribution show a strong relationship between academic pressure levels and depression risk.

### 3. Family History and Depression Percentage 
![Family History and Depression](image-4.png)

Students with a family history of mental illness tend to have a higher depression rate (approximately 61%) compared to those without such history (approximately 56%). Although the difference is not major, it shows that genetic or family environmental factors may play a role in depression tendency.

### 4. Age Distribution Based on Depression Status
![Age Distribution](image-5.png)

The number of non-depressed respondents is significantly higher than depressed respondents across almost all age groups. The distribution pattern between both groups is similar, suggesting that age does not appear to be a primary factor between depressed and non-depressed students in this case.

### 5. Depression Count by Gender
![Depression by Gender](image-6.png)

The number of students experiencing depression is higher than those who are not, in both male and female groups. The similar distribution pattern indicates that gender is not a dominant factor in depression rates in this dataset.

### 6. CGPA Distribution by Depression
![CGPA Distribution](image-7.png)

There is no significant difference in CGPA between students with depression and those without. The median and distribution of CGPA for both groups are almost identical, indicating that depression does not  affect academic performance (in terms of CGPA)

### 7. Study Satisfaction vs Depression
![Study Satisfaction](image-8.png)

Students experiencing depression have similar study satisfaction levels compared to students without depression. There is no huge difference in terms of median or value distribution.

## Model Development

After exploring the data through EDA, I built two models: **Random Forest** and **XGBoost**. The dataset was split into 80% training and 20% testing to predict the Depression label (1 = Yes, 0 = No).

### Model Selection Rationale:

**Random Forest** was chosen as the baseline model because it is:
- Easy to implement
- Stable and effective in handling non-linear relationships between variables
- Provides feature importance rankings, helping identify which factors most influence student depression

**XGBoost** was selected as an advanced boosting algorithm with:
- Better generalization ability
- Built-in regularization to prevent overfitting
- High training efficiency
- Often produces more accurate predictions

## Results 

Both Random Forest and XGBoost models demonstrated nearly identical performance metrics, achieving approximately 84% accuracy, precision, recall, and F1-score. This indicates that both algorithms are equally effective in predicting student depression based on the given features.

| Model          | Accuracy | Precision | Recall | F1-Score |
|----------------|----------|-----------|--------|----------|
| Random Forest  | 0.837    | 0.84      | 0.84   | 0.84     |
| XGBoost        | 0.838    | 0.84      | 0.84   | 0.84     |

## Conclusion
At the end, here are the important things I learned from the analysis:
- Academic pressure shows a strong correlation with depression risk
- Family history of mental illness slightly increases depression tendency
- Age and gender do not appear to be dominant factors in this case
- Depression does not significantly impact academic performance (CGPA)

These models can serve as valuable tools for early detection of depression tendencies among students, potentially facilitating timely intervention and mental health support.