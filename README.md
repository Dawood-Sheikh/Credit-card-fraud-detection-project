# Credit-card-fraud-detection-project

#### *Context*
Project about anomaly detection in credit card transactions using Azure Machine learning. 

#### *Primary Azure Technology used:*
1. AI + Machine Learning
2. Azure Machine Learning
3. Container Instances

#### *Problem Statement/Opportunity*
Identifying the fraudulent credit card transactions so that customers are not charged for the items that they did not purchase.

#### *Project Description:*
This project is created with the help of Azure machine learning studio and AutoML to find a pattern between Fraudulent and Non-fraudulent transactions. This is done with the help of Logistic Regression which found the pattern in the 30 features provided in the dataset ([more info on the dataset](https://github.com/Dawood-Sheikh/Credit-card-fraud-detection-project/blob/main/Dataset%20Info.md)) and distinguish between each transaction. An average of 97% is achieved by the models on the training data and the best model is picked and used on test data and used for deployment. The deployed model is stored in container instances
which can be used by any person when called. A more detailed explanation is given below:

##### Creating the workspace:
The first step in creating the project was creating a workspace in the Azure portal. The workspace was created with the help of Machine Learning resource. One needs to click on create button and fill in all the relevant details needed to create the workspace.
![Machine Learning Resource](https://user-images.githubusercontent.com/93479207/153747468-d6e758b1-7375-487c-86f9-9fa0abcf24ca.jpg)

After filling in all the details press **review & create** to conclude the process and wait for the deployment of the resource.
![Credit card fraud detection resource](https://user-images.githubusercontent.com/93479207/153747484-be92e7e8-9016-40c3-a85c-87b7915bb8e0.jpg)

##### Working on Machine Learning Studio

   ###### Creating Instances
   After creating the workspace one can launch Machine Learning Studio and work on creating their ML model. Before working on the actual code we need to assign a Virtual Machine for the experiment which can be done with the help of Compute Instances. It is a managed cloud-based workstation for data scientists. You can build and deploy models using integrated notebooks and the following tools in Azure Machine Learning studio:
- Jupyter
- JupyterLab
- VS Code (preview)
- RStudio (preview)
Compute instance is fully integrated with Azure Machine Learning workspace and studio. You can share notebooks and data with other data scientists in the workspace.

   ###### Importing Libraries/Dependencies
   After creating an instance we can start working on the code either on the Machine learning studio notebook or any of the integrated notebooks. Before doing data analysis on the dataset we need to import the relevant libraries and dependencies in our notebook as per the requirements.
   ![bandicam-2022-02-10-16-55-46-858](https://user-images.githubusercontent.com/93479207/153761065-44a041df-8689-40d2-95b6-db5163c3c376.gif)

   ###### Data Analysis
   After importing the libraries, the next step is uploading the dataset in the notebook. The dataset contains approx. 2.80 million transaction details of the cardholders which are already been classified into Fraudulent and Non-fraudulent transactions (1 = fraud, 0 = non-fraud). Since the dataset is so unbalanced we need to use data analysis techniques to clean and trim the dataset. The first step in data analysis is understanding the dataset and finding any null values. The next step in data analysis is to create a sample dataset containing an equal number of fraudulent and non-fraudulent transactions with the help of the under-sampling method. This new dataset will be used to train the model.
  
  
  https://user-images.githubusercontent.com/93479207/153823260-31e146e1-7da4-4b15-8f2e-8ebc3c118d66.mp4
   
   ###### Splitting the data
   After creating the ideal dataset, the next step is to split the data into features and targets, and training and test dataset. the training dataset will be used to train the model and the efficiency will be tested with the help of the testing model.
   
   ###### AutoML & Experiment
   The next step is the train the model. This was done with the help of AutoML. Since we know the problem statement is of a classification nature and the classes were already provided, therefore, Logistic Regression was used. Other models were blocked in AutoMl and an experiment 'Credit Card' was created. An average score of 97% was found in the experiments conducted with the models and among them, the best model was selected for testing.
   ![Experiment](https://user-images.githubusercontent.com/93479207/154238693-0695e48c-e603-43db-b62e-678497b89dda.jpg)

   
   ###### Best Model & Accuracy
   After getting the result from the experiment, the best run from the experiment is used as the model. The model is then tested with the testing data to see if it is predicting the answers correctly. Some other techniques were also being used to check the accuracy of the model like mean squared error and mean absolute error.
   ![best-model-_-accuracy (1)](https://user-images.githubusercontent.com/93479207/154067239-0bc46fe9-5eef-4035-92ad-dea18216d6c9.gif)
   ![Best Model](https://user-images.githubusercontent.com/93479207/154067792-0ee7f05e-d01b-4c5e-9d4b-4840214d89e4.jpg)

   ###### Registering & Deployment of the model
   After finding the best model and checking for its accuracy, now it is time for deploying the model for it to be used in production. For deploying a model, first, we have to register it in the cloud. After that, we have to import some relevant libraries/dependencies for deployment. Other things we need for deployment are the scoring file (which we get from the child run log as score.py file) and the YML file (from the environment). After running the code, ML Studio deploys the model and store it in a container instance as an endpoint(Endpoint link: http://ee497da8-5f20-4479-b6f4-bc4fc0539c47.centralindia.azurecontainer.io/score).
![Endpoint](https://user-images.githubusercontent.com/93479207/153918325-4aa91dbb-1ea2-443f-80a8-b4017d8c6d60.gif)
 ![Endpoint](https://user-images.githubusercontent.com/93479207/153925007-04217240-7610-42cc-b495-35c55a415a44.jpg)

   ###### Demo run of the Endpoint
   To see if the endpoint is working perfectly, we have run a small program that uses the model in the endpoint to predict any anomaly in the inputted transaction details and tell whether they are fraudulent or non-fraudulent by giving output as 1 or 0 (1 being fraudulent and 0 beings non-fraudulent).
 ![Deployment](https://user-images.githubusercontent.com/93479207/153920370-024993ed-abf4-4362-864b-26c56e24ba31.gif)
 
##### Acknowledgments
I would like to express my special thanks of gratitude to the mentors of Future Ready Talent who gave me the golden opportunity to do this wonderful project, which also helped me in doing a lot of research and I came to know about so many new things I am thankful to them.

The dataset has been collected and analyzed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. 
![Thank You](https://user-images.githubusercontent.com/93479207/154239427-d12353a1-8f16-4ffb-9dfe-743493d7d477.jpg)
