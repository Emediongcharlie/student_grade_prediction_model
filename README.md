# Student_grade_prediction_model

# Project Overview

This project aims to predict students’ grade classes (A, B, C, D) based on various academic, behavioral, and demographic factors.

The workflow includes:

1.  Data cleaning and preprocessing
2.  Exploratory Data Analysis (EDA)
3.  Feature engineering
4.  Model training and evaluation
5.  Deployment as an API

## 🎯 Problem Statement
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

### ✅ Handling Missing Values
```python
df.isnull().sum()
