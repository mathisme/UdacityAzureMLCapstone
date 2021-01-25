Need to Include
-- An overview of the project
-- An overview of the dataset used
-- An overview of the method used to get the data into your Azure ML Studio workspace.
-- An overview of your AutoML experiment settings and configuration
-- An overview of the types of parameters and their ranges used for the hyperparameter search
-- An overview of the two models with the best parameters
-- An overview of the deployed model and instructions on how to query the endpoint with a sample input
-- A short overview of how to improve the project in the future


# Your Project Title Here

## Project Overview 

For Udacity's Machine Learning Engineer with Microsoft Azure Nanodegree capstone project we had to 

## Dataset

### Overview

The dataset used is the Heart Failure clinical records Data Set that can be found [here](https://archive.ics.uci.edu/ml/datasets/Heart+failure+clinical+records) at the UCI Machine Learning repository.  For the project I was browsing the UCI machine learning repository for datasets to use as these sets are smaller than ones found on other sites such as data.gov.  After looking through the daasets, this one was of particular interest due to having a family history of heart disease.

The dataset is comprised of 299 records of heart failure patients with 13 attributes and no missing values.  All attributes are numeric consisting of both continuous and discrete values.  

// the variable of interest is DEATH_EVENT



### Task
*TODO*: Explain the task you are going to be solving with this dataset and the features you will be using for it.

// explain how doctors could use this.
Upon predicting of a possible death event, doctors may want to call patients in for a further checkup or switch medications or dosages
// what else? ^

### Access
*TODO*: Explain how you are accessing the data in your workspace.
// for both hyperdrive and automl
In both notebooks the dataset was read in using Dataset.Tabular.from_delimited_files using the url of that dataset at the UCI machine learning repository site.
It was then registered in Azure if it hadn't been already.
// talk about train test split

Fot hyperdrive, the train.py file reads the data in the same way, converts it to a pandas dataframe, pops Death Event off and splits it into a training and test set 
// want to say using same random seed

// need to say what is done with the training set for automl


## Automated ML
*TODO*: Give an overview of the `automl` settings and configuration you used for this experiment
Experiment timeout 30 minutes
The training was done remotely
Primary metric of accuracy // why
5 cross validations // why
early stopping enabled // need to read more about this.  What is early sopping
classification task, data being the training set, label column name being DEATH_EVENT



### Results
*TODO*: What are the results you got with your automated ML model? What were the parameters of the model? How could you have improved it?

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.

## Hyperparameter Tuning
*TODO*: What kind of model did you choose for this experiment and why? Give an overview of the types of parameters and their ranges used for the hyperparameter search
### Model

### Hyperparameters chosen

### Settings

### Results
*TODO*: What are the results you got with your model? What were the parameters of the model? How could you have improved it?

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.

## Model Deployment
*TODO*: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.

// Be sure to state which model is deployed

// Be sure to include a screenshot of the endpoint

## Screen Recording


## Suggestions

// put in order of what you want to do right away

* Require authentication to access the endpoint
To avoid attacks against the endpoint, authorization should be required.
 
* Use recall instead of accuracy for the primary metric
With DEATH_EVENT being the y value, recall should be used as the primary metric instead of accuracy as a false negative is literally deadly.  I plan to change this in the near future but because the end of the nanodegree is near, I am keeping accuracy as the primary metric when submitting my capstone.

* Hyperdrive: Exploratory data analysis and feature selection
Other than using every attribute, an exploratory data analysis with feature selection prior to training would improve the HyperDrive performance.  Having taken a course in linear regression, I know how to determine what features to include or exclude for linear regression models.  However I am presently uncertain how to do feature selection for classificcation problems.  

* Hyperdrive: Save the training set to storage so train.py doesn't split it every call

* Hyperdrive: Test the model before registering it
* AutomatedML: Enable the use of deep neural networks
* Create a swagger schema
* Enable Application Insights
