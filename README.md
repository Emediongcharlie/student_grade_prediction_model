# Student_grade_prediction_model

# Project Overview

This project aims to predict students’ grade classes (A, B, C, D) based on various academic, behavioral, and demographic factors.

The workflow includes:

1.  Data cleaning and preprocessing
2.  Exploratory Data Analysis (EDA)
3.  Feature engineering
4.  Model training and evaluation
5.  Deployment as an API

---

## Problem Statement
Educational institutions often struggle to identify students at risk of poor performance early.

This system helps:
- Predict student outcomes
- Identify key performance factors
- Support data-driven academic decisions

---

## Dataset Description

The dataset contains various student-related features:

| Feature | Description |
|--------|------------|
| StudentID | Unique identifier |
| Gender | Male/Female |
| Age | Student age |
| Ethnicity | Student background |
| ParentalEducation | Parent education level |
| ParentalSupport | Support level (0/1) |
| StudyHours | Daily study hours |
| StudyTimeWeekly | Weekly study time |
| Absences | Number of absences |
| GPA | Grade Point Average |
| Extracurricular | Participation (0/1) |
| Sports | Participation (0/1) |
| Music | Participation (0/1) |
| Volunteering | Participation (0/1) |
| Tutoring | Extra academic support |
| GradeClass | Target variable (A, B, C, D) |

---

## Data Cleaning

Key preprocessing steps:

### Handling Missing Values
```python
df.isnull().sum()

Missing values were identified and handled appropriately.

### Data Type Correction
```python
df['Gender'] = df['Gender'].astype('category')

### Binary Encoding

### Duplicate Removal
```python
df.drop_duplicates(inplace=True)

## Exploratory Data Analysis
Done with Seaborn and Matplotlib

## Insights

- Strong positive correlation between study hours and GPA
- Students involved in extracurricular activities performed better that those not involved
- We had more female involved in extracurricular activities than male
- There was a strong positive correlation between study hours and GPA
- There was a strong negative correlation between absenses and GPA

## Data Preprocessing

Achieved through column seperation and transformation pipeline to achieve:
- Scales numerical features
- Encodes categorical variables
- Prevents data leakage
- Ensures consistent pipeline during deployment

## Model Training

This is a classification problem and so Mmodel Used was Logistic Regression

## Model Evaluation
Accuracy_score was :
98.7%
Classification Report:
- High precision and recall across most classes
- Slight drop for minority classes
Confusion Matrix Insights:
- Most predictions are correct
- Minor confusion between adjacent grades (C ↔ D)

## Deployment (FastAPI)

The model is deployed as a REST API for real-time predictions.
```python
POST /predict

### Example request
```JSON
{
  "StudentID": 12345,
  "Gender": "Male",
  "Age": 16,
  "Ethnicity": "Hispanic",
  "ParentalEducation": "Bachelor",
  "ParentalSupport": 1,
  "Tutoring": 0,
  "Extracurricular": 1,
  "Sports": 0,
  "Music": 1,
  "Volunteering": 0,
  "StudyHours": 5,
  "StudyTimeWeekly": 10,
  "Absences": 2,
  "GPA": 3.5
}

### Example Response

```JSON
{
  "prediction": "A"
}

## Tech Stack

- Programming: Python
- Data Processing: Pandas, NumPy
- Visualization: Matplotlib, Seaborn
- Machine Learning: Scikit-learn
- Deployment: FastAPI, Uvicorn

## Challenges Faced
- Handling categorical variables in ML models
- Fixing scaling errors caused by string values
- Had more A grade data


