# Credit-Card-Fraud-Detection-Project
Credit Card Fraud Detection using Logistic Regression

**About the dataset** :
The data was taken from Kaggle site : https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud .

The Columns do not have physical significance directly visible since as per the source (Kaggle) , the data was compressed using Principle Component Analysis (PCA) in order to protect the privacy of the individuals while making a realistic secnario dataset availaible to public .
# **Data Preprocessing and Visualisation** :

![image](https://github.com/user-attachments/assets/e0748509-80b6-4cc7-8337-df057c49f0da)

# Correlations :
 ![image](https://github.com/user-attachments/assets/de191efe-8527-4802-b9aa-1ad9221a8512)
![image](https://github.com/user-attachments/assets/893dcc2b-8e6b-40f2-a3f3-484584e8c58d)

The columns do not seem to have correlations with each other , and seem to have great correlation with the Class and time variables , hence being a great indicator that simple models would be helpful here , and neural networks wont be needed hopefully .

![image](https://github.com/user-attachments/assets/1f624467-cccb-4e73-b749-107b80fcb254)
![image](https://github.com/user-attachments/assets/ad6bbe03-4c1d-454f-99cf-0f96f0d6c712)
A plot between different columns and amount along with different colours for target variable show that our output classes are separable by linear boundary even in case of graphing variables alone , hence LOGISTIC REGRESSION will help separate the multivariable data into 2 classes .
![image](https://github.com/user-attachments/assets/8d4838e8-cf17-44ba-ba65-cfda6fecb95e)
This shows that we have way way less data for fraud cases than for non fraud cases , which is expected from the dataset .

To cure imbalance , we can use undersampling or oversampling . Here , I have decided to use SMOTE to counter the class imbalance in the dataset 

![image](https://github.com/user-attachments/assets/f9031440-e7c9-4c68-96bf-a76eccf181d8)
# Training the model :
![image](https://github.com/user-attachments/assets/dff24026-1260-41d6-81e9-21f6c2425ab7)
I have trained a Logistic Regression Model here . The model was showing a not converging warning , so I read its documentation and added the code to make it run for 150 iterations .

**Results from part 1** :

![image](https://github.com/user-attachments/assets/b4451b8e-004f-4298-9abb-7d8598471e76)

The F1 score came 0.99 meaning the Classifier is working great . It managed to catch 91 out of 101 frauds , thus preventing frauds 90% of the time . The confusion matrix , precision , recall and F1 score has been displayed for your convenience . The confusion matrix readings and the F1 show the success of the project .

![image](https://github.com/user-attachments/assets/66d4d8d2-d8c4-4d6e-82ff-2854eefcd57b)

Results from part 2 :
I have also uploaded some raw code to this repository , here are the conclusions derived from it :

Frauds are time independent so we can drop time :

![image](https://github.com/user-attachments/assets/fe4c403c-edb2-4312-8a24-a2572bcdbcc6)
* Results with dimesnsionality reduction !
  
![image](https://github.com/user-attachments/assets/e1807f15-6fbf-464c-b0d9-e837ddfa844c)

I decided to undersample the dataset since significance of the data would be more realistic if there was no synthetic dataset. I also decided to choose the ML model with most recall , reason being that I realized later that as a business, labelling a Non Fraud datapoint as fraudulent would be much more worse for the company, since nobody would like their card to decline and people would literally stop using that credit card, so we must focus more on achieving lower recall than only blindly improving F1 score . So I got Logistic regression as the winner again with the following results :

![image](https://github.com/user-attachments/assets/87ec5f16-90c5-4fc6-ae63-7c3f53c1f712)
