# WiDS Datathon 2025 - Team Conscious

### **👥 Team Members**

| Name | GitHub Handle | Contribution |
| ----- | ----- | ----- |
| Tiffany Fu | @tiffanyfu7 | Completed model exploration with CNN and LR, Handle Missing Data |
| Zaina Mushtaq | @zainamushtaq | Led Feature Engineering and Model Evalution |
| Xinyue Su | @Xinyue519 | Built and Optimized Neural Network Model, Feature Engineering and Missing Data Handling |
| Alison Sanchez | @AlThe5th | Built and Optimized Logistic Regression Model |

*NOTE: feel free to edit your contributions here!!!*

## TODO: Add Table of Contents

## **🎯 Project Highlights**
* Built a Neural Network Model and a Logistic Regression Model to predict individual's sex and ADHD Diagnosis
* Achieved an F1 score of \[insert score\] and \[insert score\] respectively
* Placed 19 out of 539 Teams (Top 0.03%)
  
* Used \[explainability tool\] to interpret model decisions
* Implemented \[data preprocessing method\] to optimize results within compute constraints


🔗 [WiDS Datathon 2025 | Kaggle Competition Page](https://www.kaggle.com/competitions/widsdatathon2025/overview)

---

## **👩🏽‍💻 Setup & Execution**
#### 1. Retreive our Code by Cloning this Repository or Downloading the Notebooks

  > To Clone the Repo Run `git clone https://github.com/wids-teamConscious/monorepo`


#### 2. Download Datasets Through WiDS Kaggle Competition Page
   
> Visit [Data Tab](https://www.kaggle.com/competitions/widsdatathon2025/data) at Kaggle Competition Page and Click `Download All`

#### 3. Replace File Paths to Data

#### 4. Press Run All to Run Notebook

#### 5. Retreive Test Predictions 
> Results stored in `neuralNetworkPredictions.csv` and `logisticRegressionPredictions.csv`
---

## **🏗️ Project Overview**

**Describe:**

* The Kaggle competition and its connection to the Break Through Tech AI Program
* The objective of the challenge
* The real-world significance of the problem and the potential impact of your work

---

## **📊 Data Exploration**

**Describe:**

* The dataset(s) used (i.e., the data provided in Kaggle \+ any additional sources)
* Data exploration and preprocessing approaches
* Challenges and assumptions when working with the dataset(s)

**Potential visualizations to include:**

* Plots, charts, heatmaps, feature visualizations, sample dataset images

---

## **🧠 Model Development**


**Neural Network Model**

We decided to go for a Neural Network model because it excels at analyzing complex, non-linear data. We realized traditional models, such as RandomForest, failed to learn the trend and pattern. This model helped us achieve the 0.77918 score on the Kaggle Leaderboard.

Below are the features, hyperparameters, and set up we have for the model:

* Used leakyReLU to avoid dead neurons
* Used Dropout to prevent overfitting, BatchNormalization to improve training stability
* Used EarlyStopping to prevent overfitting and improve model efficiency
* Implemented train_test_spilit with 30% test size, accuracy as evaluation metric, and binary_crossentropy for loss


---

## **📈 Results & Key Findings**

**Describe (as applicable):**

* Performance metrics (e.g., Kaggle Leaderboard score, F1-score)
* How your model performed overall
* How your model performed across different skin tones (AJL)
* Insights from evaluating model fairness (AJL)


**Potential visualizations to include:**

* Confusion matrix, precision-recall curve, feature importance plot, prediction distribution, outputs from fairness or explainability tools

---

## **🖼️ Impact Narrative**

**Answer the relevant questions below based on your competition:**

**WiDS challenge:**

1. What brain activity patterns are associated with ADHD; are they different between males and females, and, if so, how?
2. How could your work help contribute to ADHD research and/or clinical care?

---

## **🚀 Next Steps & Future Improvements**

**Address the following:**
* What are some of the limitations of your model?
* What would you do differently with more time/resources?
* What additional datasets or techniques would you explore?

---

## **📄 References & Additional Resources**

* Cite any relevant papers, articles, or tools used in your project

---
