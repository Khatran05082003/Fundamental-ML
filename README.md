# Mini-Project for Fundamentals of Machine Learning Course
![background](./materials/ai_wp.jpg)
This repository contains the code and data for a mini-project on facial expression recognition using machine learning algorithms.

## 📑 Project Policy
- Team: group should consist of 3-4 students.

    |No.| Student Name    | Student ID |
    | --------| -------- | ------- |
    |1|Nguyễn Hoàng Thông|21280075|
    |2|Trần Tuấn Kha|21280092|
    |3|Phạm Trường|21280116|
    |4|||

- The submission deadline is strict: **11:59 PM** on **June 22nd, 2024**. Commits pushed after this deadline will not be considered.

## 📦 Project Structure

The repository is organized into the following directories:

- **/data**: This directory contains the facial expression dataset. You'll need to download the dataset and place it here before running the notebooks. (Download link provided below)
- **/notebooks**: This directory contains the Jupyter notebook ```EDA.ipynb```. This notebook guides you through exploratory data analysis (EDA) and classification tasks.

## ⚙️ Usage

This project is designed to be completed in the following steps:

1. **Fork the Project**: Click on the ```Fork``` button on the top right corner of this repository, this will create a copy of the repository in your own GitHub account. Complete the table at the top by entering your team member names.

2. **Download the Dataset**: Download the facial expression dataset from the following [link](https://mega.nz/file/foM2wDaa#GPGyspdUB2WV-fATL-ZvYj3i4FqgbVKyct413gxg3rE) and place it in the **/data** directory:

3. **Complete the Tasks**: Open the ```notebooks/EDA.ipynb``` notebook in your Jupyter Notebook environment. The notebook is designed to guide you through various tasks, including:
    
    1. Prerequisite
    2. Principle Component Analysis
    3. Image Classification
    4. Evaluating Classification Performance 

    Make sure to run all the code cells in the ```EDA.ipynb``` notebook and ensure they produce output before committing and pushing your changes.

5. **Commit and Push Your Changes**: Once you've completed the tasks outlined in the notebook, commit your changes to your local repository and push them to your forked repository on GitHub.


Feel free to modify and extend the notebook to explore further aspects of the data and experiment with different algorithms. Good luck.


1. **Question 1**: Can you visualize the data projected onto two principal components? (2 points)

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/c12e06f8-e339-496d-8a68-abd34d8b9ea2)


2. **Question 2**: How to determine the optimal number of principal components using ```pca.explained_variance_```? Explain your selection process.

The selection process:

Eigenvalues Calculation: For each number of PCs (from 1 to 20), PCA is performed on the data, and the eigenvalues are calculated. These eigenvalues represent the amount of variance captured by each principal component.

Storing Last Eigenvalue: The last eigenvalue for each number of PCs is stored in a dictionary. Because when increasing the number of PCs, each additional PC will capture less variance.

Plotting Eigenvalues: A plot is created to visualize how eigenvalues change with different numbers of PCs.

Eigenvalue Cutoff: A horizontal line is drawn at eigenvalue = 1. It suggests that we should only keep PCs with an eigenvalue greater than 1, as they add significant information.

Determining Optimal Components: Iterate through the dictionary to find the maximum number of components where the last eigenvalue is greater than or equal to 1.

Result: The optimal number of principal components is found, which represents the number of PCs that have significant eigenvalues (≥ 1).

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/ee88c71e-c9dc-43ad-9fcd-6fa0f91ecbf8)


![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/5c6c94e5-95d6-40ee-8be1-8690eb1330a3)


Based on the figure above, we can determine the optimal number of Principal Components is 5. This is the point at which the curve begins to flatten (elbow). After this point, adding more Principal Components does not contribute too much to increasing the explained variance ratio.

3. **Question 3**: Compare the performance of **4** different classification algorithms (3 machine learning and 1 MLP models) in both formats above. (4 points)
#### Original data
#### Confusion matrix
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/115189da-3492-41f3-a663-b38c871ba225)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/329c54d6-46f7-47c2-ab38-4aa07cd377a5)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/11804c5e-b012-4819-af33-8367a1fc58d1)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/2c0be780-d8d3-447a-987b-787c6222a600)

#### Classification report
Linear Logistic

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/7f71b4a8-1ba5-4a95-aa59-76a9e3181714)

SVM

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/7fc0a4cc-720c-4a67-8e60-34eaf82dc9c5)

Naive Bayes

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/8259b41c-14f3-4028-80f6-7a7722f4ea6e)

MLP

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/a940303e-5112-4b8e-9840-422134e0d885)


#### Transformed data
#### Confusion matrix
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/a0c7e54d-2e82-409c-bbc6-e8fefd014af1)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/f17835c9-1f2f-4df8-92d0-0aaed5272d21)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/0b9c96d4-409e-4e8e-b4ef-7e96a6024b33)
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/77d9294c-4ae5-4f2a-b8be-7461777b4052)
#### Classification report
Linear Logistic

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/92891b35-d512-47f5-b00a-7a304c70b5d4)

SVM

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/531eebdd-93cc-46d0-903d-cf7ab9c0873f)

Naive Bayes

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/16617d65-1c87-4643-b546-7fdab2cb3cfc)

MLP

![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/dbf05c7e-c632-4d9e-b4f0-62e97993517a)

4. **Question 4**: Perform hyperparameter tuning using ```GridSearchCV``` for each classification method. (1 point)

Best hyperparameter tuning using ```GridSearchCV``` for each classification method are:

    LogisticRegression(C=0.1, max_iter=100),
    SVC(C=0.1, gamma=0.01, kernel='rbf'),
    GaussianNB(priors=None, var_smoothing=0.001),
    MLPClassifier(alpha=0.01, max_iter=200)

5. **Question 5**: Compare the performance of the different classification models using various metrics: accuracy, precision, recall, and F1-score.
Based on the evaluation metrics, explain which model performs best and why. Identify the emotion category where the model makes the most accurate and most errors.

Original data:
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/0dcff04f-52e7-42e8-b3eb-5d14ffbcd72b)

Transformed data:
![image](https://github.com/Khatran05082003/Fundamental-ML/assets/102920168/e4856999-48cc-4ccc-bb39-e9afe98700e2)


Based on the table above, the GaussianNB model seems to perform best on transformed data.

GaussianNB has a mean of 0.261939, which is the highest among the models listed, indicating good average performance.

GaussianNB also has the lowest standard deviation (0.002131) among all models, suggesting it delivers the most consistent results across different runs or datasets.

In conclusion, considering both accuracy (mean) and reliability (standard deviation), GaussianNB appears to offer the best balance of performance applying on transformed data.

The emotion category where the model makes the most accurate is *Happy* and most errors is *Angry*.


