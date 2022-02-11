# Credit-card-fraud-detection-project

#### *Context*
Project about anomaly detection in credit card transactions using Azure Machine learning. 

#### *Primary Azure Technology used:*
*1.* AI + Machine Learning
*2.* Azure Machine Learning
*3.* Container Instances

#### *Problem Statement/Opportunity*
Identifying the fraudulent credit card transactiions so that customers are not charged for the items that they did not purchase.

#### *Project Description:*
  This project is created with the help of Azure machine learning studio and AutoML in order to find a pattern betweeen Fraudulent and Non-fraudulent transactions. This is done with
the help of Logistic Regression which found the pattern in the 30 features provided in the dataset ([more info on the dataset](https://github.com/Dawood-Sheikh/Credit-card-fraud-detection-project/blob/main/Dataset%20Info.md)) and distinguish between each transactions. An average 
of 97% is acheived by the models on the training data and the best model is picked and used on test data and used for deployment. The deployed model is stored in container instances
which can be used by any person when called. More detailed explanation is given below:

##### Creating the workspace:
First step in creating the project was creating a workspace in Azure portal. Workspace was created with the help of 
