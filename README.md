# WiDS Datathon 2025 - Team Conscious

### **👥 Team Members**

| Name | GitHub Handle | Contribution |
| ----- | ----- | ----- |
| Tiffany Fu | @tiffanyfu7 | Completed model exploration with CNN and LR, Handle Missing Data |
| Zaina Mushtaq | @zainamushtaq | Led Feature Engineering and Model Evaluation |
| Xinyue Su | @Xinyue519 | Built and Optimized Neural Network Model |
| Alison Sanchez | @AlThe5th | Built and Optimized Logistic Regression Model |


---


## **📋 Table of Contents**  
1. [**🎯 Project Highlights**](#project-highlights)  
2. [**👩🏽‍💻 Setup & Execution**](#setup--execution)  
3. [**🏗️ Project Overview**](#project-overview)  
4. [**📊 Data Exploration**](#data-exploration)  
5. [**🧠 Model Development**](#model-development)  
6. [**🖼️ Impact Narrative**](#impact-narrative)  
7. [**🚀 Next Steps & Future Improvements**](#next-steps--future-improvements)  
8. [**📄 References & Additional Resources**](#references--additional-resources)  


---

## **🎯 Project Highlights**
* Built a Neural Network Model and a Logistic Regression Model to predict individual's sex and ADHD Diagnosis
* Achieved an F1 score of 0.701and 0.652 respectively
* Placed 19 out of 539 Teams (Top 0.03%)
* Implemented Filling Missing Values and Standard Scaler to optimize results within compute constraints

---

## **👩🏽‍💻 Setup & Execution**
#### 1. Retrieve our Code by Cloning this Repository or Downloading the Notebooks

  > To Clone the Repo Run `git clone https://github.com/wids-teamConscious/monorepo`

#### 2. Download Datasets Through WiDS Kaggle Competition Page
   
> Visit [Data Tab](https://www.kaggle.com/competitions/widsdatathon2025/data) at Kaggle Competition Page and Click `Download All`

#### 3. Replace File Paths to Data
```
categorical_path = ‘<INSERT PATH>’
functiontional_path = ‘<INSERT PATH>’
quantative_path = ‘<INSERT PATH>’
target_path = ‘<INSERT PATH>’

df_categorical = pd.read_excel(categorical_path)
df_functional = pd.read_csv(function_path')
df_quantitative = pd.read_excel(quantitative_path)
df_target = pd.read_excel(target_path)
```
#### 4. Press `Run All` to Run Notebook

#### 5. Retrieve Test Predictions 
> Results stored in `neuralNetworkPredictions.csv` and `logisticRegressionPredictions.csv`

---

## **🏗️ Project Overview**
The **WiDS Datathon Global Challenge** was developed in collaboration with the [Ann S. Bowers Women’s Brain Health Initiative](https://wbhi.ucsb.edu/) (WBHI), Cornell University, and UC Santa Barbara. The datasets and support for this challenge were provided by the Healthy Brain Network (HBN), the signature scientific initiative of the Child Mind Institute, and the Reproducible Brain Charts project (RBC).  

As **Spring 2025 [Break Through Tech AI Fellows](https://www.breakthroughtech.org/)** — a Cornell Tech initiative dedicated to empowering and connecting undergraduate students from diverse backgrounds to influential tech opportunities — we participated in this competition to tackle a critical issue in neuropsychiatric health.  

#### Objective of the Challenge  
Our project focused on predicting an individual's sex and ADHD diagnosis using AI/ML models. Neuropsychiatric disorders that emerge in childhood, such as anxiety, depression, autism, and attention deficit hyperactivity disorder (ADHD), often present differently across sexes. Research suggests that ADHD in girls frequently goes undiagnosed because they tend to exhibit inattentive symptoms rather than hyperactivity, making their condition harder to detect.  

#### Real-World Significance and Potential Impact  
Undiagnosed ADHD in girls can lead to long-term challenges, including struggles with academic performance, self-esteem, mental health, and daily functioning. By leveraging machine learning, we aimed to improve ADHD detection in females, reducing the likelihood of missed diagnoses and enabling earlier intervention. This work has the potential to contribute to more equitable and personalized mental health care, ensuring that individuals receive the support they need based on their unique neurobiological profiles.  

🔗 [WiDS Datathon 2025 | Kaggle Competition Page](https://www.kaggle.com/competitions/widsdatathon2025/overview)


---


## **📊 Data Exploration**
#### Datasets used
Data provided in Kaggle as mentioned in Setup
Data sets included quantitative, categorical, and functional training data

#### Exploration and Preprocessing Approaches
First began by combing through all of the datasets and variables, understanding what different values meant in terms of measurement for certain columns, etc. This included a thorough comb through of the “Data Dictionary” provided by Kaggle. 

First preprocessing step was to find and take care of all null values.

For quantitative variables, missing values were replaced with either the mean or median of the column depending on the skew of that variable 

<img width="975" alt="Screenshot 2025-03-22 at 3 08 27 PM" src="https://github.com/user-attachments/assets/13cf9990-a13a-4fb1-b88b-aa66e7df0e89" />

For categorical variables, missing values were replaced with the mode of the column. Columns with over 200 missing values were dropped completely, as that accounts for almost 17% of the data. One-hot encoding was not needed as the categorical variables already came one-hot encoded in numerical form.  Finally, some categorical variables had repetitive values that could be combined as they essentially meant the same thing in terms of data. For example, the “Ethnicity” column contained both “Decline to specify” and “Unknown,” which, for data processing purposes, just means no value. Another example is parents’ occupation, where blue-collar jobs were combined into one value and jobs requiring higher education were combined into another. 

#### Challenges and Assumptions
The biggest initial challenge we had was actually the data preparation and preprocessing itself. When first exploring the data, we could not understand what to actually do to the data before modeling. Since parent 2’s education and occupation each had 200+ missing values, we dropped those columns completely and assumed it will not affect the modeling too much. 


---


## **🧠 Model Development**

#### Logistic Regression Model

We started with a logistic regression model as a baseline for overall model development. We also messed around with wrapper functions to try and improve performance, however none could predict better than the base logistic model with optimized parameters.

Below is the setup for this model:

* Tailored model for both labels
* Performed GridSearch to find optimal LR parameters for each label
* 70/30 train/test split
* Used StandardScaler on X_train and X_test
* Using primarily F1-Score and accuracy evaluation metrics.
* ADHD: 77-82% accuracy, 80-85% F1
* Sex: 66-73% accuracy, <54% F1
  
#### Neural Network Model

We decided to go for a Neural Network model because it excels at analyzing complex, non-linear data. We realized traditional models, such as RandomForest, failed to learn the trend and pattern. This model helped us achieve the 0.77918 score on the Kaggle Leaderboard.

Below are the features, hyperparameters, and set up we have for the model:

* Used leakyReLU to avoid dead neurons
* Used Dropout to prevent overfitting, BatchNormalization to improve training stability
* Used EarlyStopping to prevent overfitting and improve model efficiency
* Implemented train_test_spilit with 30% test size, accuracy as evaluation metric, and binary_crossentropy for loss


---


## **📈 Results & Key Findings**

|                     | Kaggle Leaderboard Score | ADHD Model F-1 Score | Sex Model F-1 Score |
|---------------------|--------------------------|----------------------|---------------------|
| Logistic Regression | 0.74620                  | 0.818                | 0.626               |
| Neural Network      | 0.77918                  | 0.821                | 0.55                |


---


## **🖼️ Impact Narrative**

The top ten features of our Logistic Regression Model for predicting Sex Output point to the biggest predictors between male and female participants

| Top Feature                | Coefficient |
|----------------------------|-------------|
| 52throw_53thcolumn         | 0.448153    |
| 50throw_53thcolumn         | 0.443506    |
| 121throw_147thcolumn       | 0.432214    |
| 164throw_189thcolumn       | 0.429034    |
| 114throw_121thcolumn       | 0.427718    |
| 53throw_55thcolumn         | 0.423922    |
| 101throw_131thcolumn       | 0.422798    |
| 160throw_190thcolumn       | 0.411727    |
| MRI_Track_Scan_Location_4  | 0.407417    |
| Barratt_Barratt_P1_Edu_9   | 0.404300    |

These results highlight the difference in brain patterns particularly in the diagonal which could be further supported by ADHD research


---


## **🚀 Next Steps & Future Improvements**

#### Limitations of Our Model
One key limitation of our neural network is **explainability**—a common challenge with deep learning models. Neural networks function as black boxes, making it difficult to interpret how specific predictions are made. This lack of transparency can limit trust and adoption in medical and clinical settings. In future iterations, we plan to integrate explainability tools such as **SHAP (SHapley Additive Explanations)** and **LIME (Local Interpretable Model-agnostic Explanations)** to provide better insights into feature importance and model decision-making.  

#### Improvements with More Time and Resources
With additional time and resources, we would focus on:  
* Enhancing workflow efficiency: Implementing a more structured organization for shared files and datasets to improve team collaboration and reproducibility. 
* Bias and fairness analysis: Conducting deeper evaluations to ensure our model does not reinforce existing biases in ADHD diagnosis across different demographics.  

#### Future Exploration 
In future projects, we would like to explore:  
* Ensemble learning techniques: Combining multiple models (e.g., Random Forest, Gradient Boosting, and Neural Networks) to improve predictive performance and robustness.  
* Multi-modal data integration: Incorporating additional datasets, such as **genetic data, neuroimaging scans, and behavioral assessments**, to provide a more comprehensive understanding of ADHD diagnosis.  
* Transfer learning: Leveraging pre-trained models in medical AI to enhance performance without requiring an extensive labeled dataset.  


---


## **📄 References & Additional Resources**
[Sex-Specific Differences in the Healthy and Disordered Brain | WiDS Worldwide](https://www.youtube.com/watch?v=KO7YI7j_d-A)

[Introduction to The Healthy Brain Network](https://www.youtube.com/watch?v=GVEemkLwz-k)

[​​Deep learning for sex classification in resting-state and task functional brain networks from the UK Biobank | Leming et. al](https://pmc.ncbi.nlm.nih.gov/articles/PMC8456752/)
