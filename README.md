# End-to-end Heart Disease Prediction Project

The goal of this project was putting together a proof of concept of predicting heart disease using machine learning, given a set of patient records (binary classification problem). The data used is featured on Kaggle, which was subsequently sourced from the UCI Machine Learning Repository.

https://archive.ics.uci.edu/ml/datasets/heart+Disease

### The Environment
- Python3
- Pandas, Numpy, Matplotlib, Scikit-Learn, Seaborn
- Jupyter Notebook

### 1. Problem Definition
Can we predict whether or not a patient has heart disease, given relevant clinical parameters of patients?

### 2. Data
The dataset originates from the Cleveland database from the UCI Machine Learning Repository, which has been formatted and is now featured on Kaggle: https://www.kaggle.com/ronitf/heart-disease-uci/

The original database contains 76 attributes (independent variables), of which 14 attributes will be used for our machine learning problem to determine heart disease (dependent variable).

### 3. Evaluation
The evaluation metric for this project is an overall **accuracy score**. If we can reach 95% accuracy at predicting whether or not a patient has heart disease during the proof of concept, we might choose to pursue this project.

### 4. Features 
The following are the features we'll use to predict our target variable (heart disease or no heart disease).

1. age - age in years
2. sex - (1 = male; 0 = female)
3. cp - chest pain type
    * 0: Typical angina: chest pain related decrease blood supply to the heart
    * 1: Atypical angina: chest pain not related to heart
    * 2: Non-anginal pain: typically esophageal spasms (non heart related)
    * 3: Asymptomatic: chest pain not showing signs of disease
4. trestbps - resting blood pressure (in mm Hg on admission to the hospital); anything above 130-140 is typically cause for concern
5. chol - serum cholestoral in mg/dl; serum = LDL + HDL + .2 * triglycerides; above 200 is cause for concern
6. fbs - (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false); '>126' mg/dL signals diabetes
7. restecg - resting electrocardiographic results
    * 0: Nothing to note
    * 1: ST-T Wave abnormality
        * can range from mild symptoms to severe problems
        * signals non-normal heart beat
    * 2: Possible or definite left ventricular hypertrophy
        * Enlarged heart's main pumping chamber
8. thalach - maximum heart rate achieved
9. exang - exercise induced angina (1 = yes; 0 = no)
10. oldpeak - ST depression induced by exercise relative to rest
    * looks at stress of heart during excercise
    * unhealthy heart will stress more
11. slope - the slope of the peak exercise ST segment
    * 0: Upsloping: better heart rate with excercise (uncommon)
    * 1: Flatsloping: minimal change (typical healthy heart)
    * 2: Downslopins: signs of unhealthy heart
12. ca - number of major vessels (0-3) colored by flourosopy
    * colored vessel means the doctor can see the blood passing through
    * the more blood movement the better (no clots)
13. thal - thalium stress result
    * 1,3: normal
    * 6: fixed defect: used to be defect but ok now
    * 7: reversable defect: no proper blood movement when excercising
14. target - have disease or not (1=yes, 0=no) (= the predicted attribute)

**NOTE:** No personal identifiable information (PPI) can be found in the dataset.

### 5. Modeling
We'll be using the following Scikit-Learn classifaction models to explore the POC viability:

* Logistic Regression Classifer - LogisticRegression()
* K-Nearest Neighbors Classifer - KNeighboursClassifier()
* RandomForest Classifier - RandomForestClassifier()

### The Conclusion
Unfortunately we are unable to predict whether or not a patient has heart disease, given relevant clinical parameters of patients. The project results were as follows:

* Logistic Regression Classifer: 0.8852459016393442
* K-Nearest Neighbors Classifer: 0.6885245901639344
* RandomForest Classifier: 0.8688524590163934

A maximum cross-validated accuracy score of **88.52%** was achieved using the **Logistic Regression Classifer**, which is below the acceptable target of 95%. Data-related issues such as class-imbalance and the overall dataset size may need to be addressed to improve these results. Additionally, some alternative model libraries (e.g. CatBoost or XGBoost) could feature some classifiers that may yield better results.
