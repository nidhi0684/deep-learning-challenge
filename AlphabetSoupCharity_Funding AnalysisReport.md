# Module 21 Challenge - AlphabetSoupCharity Funding Analysis Report

![Image](./Images/FundingAnalysis.jpg)

## Table of Contents:
1. [Overview of the Analysis](#overview-of-the-analysis)
2. [Model Results](#results)
3. [Summary](#summary)

### Final Analysis and Report on the Neural Network Model

Given below is my Final Report and Analysis of the Neural Network Model along with answers to the questions posed in the challenge:

## Overview of the Analysis

- Explain the purpose of this analysis.
  - The purpose of the model was to create an algorithm to help Alphabet Soup, predict whether or not applicants for funding will be successful. The model was a binary classifier that was able to predict with a fairly high degree of accuracy if the funding will be successful or not.


 ## Results

 Using bulleted lists and images to support your answers, address the following questions: 

  - **Data Preprocessing**
    - What variable(s) are considered the target(s) for your model?
      - The variable for the Target was identified as the column IS_SUCCESSFUL.

    - What variable(s) are considered to be the features for your model?
      - The following columns were considered as features for the model:
        - ``NAME``
        - ``APPLICATION_TYPE``
        - ``AFFILIATION``
        - ``CLASSIFICATION``
        - ``USE_CASE``
        - ``ORGANIZATION``
        - ``STATUS``
        - ``INCOME_AMT``
        - ``SPECIAL_CONSIDERATIONS``
        - ``ASK_AMT``
    - What variable(s) are neither targets nor features, and should be removed from the input data?
      - The column or variable that can be removed is EIN as it is an identifier for the applicant organization and has no impact on the behavior of the model.

- **Compiling, Training, and Evaluating the Model**

  - How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - In the Optimized version of the model, I used 3 hidden layers each with multiple neurons which increased the accuracy to <75% to 79%. The Initial model had only 2 layers. Although the number of epochs did not change between the Initial and the Optimized Model, adding a 3rd Layer increased the accuracy of the model.
  
  - Were you able to achieve the target model performance?
    - Yes by optimizing the model, I was able to increase the accuracy from 72% a little over 79%.

  - What steps did you take to try and increase model performance? 
    - The following steps were taken to optimize and increase the performance of the model:
      - Instead of dropping both the EIN and Name columns, only the EIN column was dropped. However, only the names which appeared more than 5 times were considered.
      - Added a 3rd Activation Layer to the model in the following order to boost the accuracy to > 75% :

        - 1st Layer - relu
        - 2nd Layer - tanh
        - 3rd Layer - sigmoid
      - It was observed that instead of both the 2nd and 3rd Layer to be sigmoid, when I used the 2nd Layer as tanh and the 3rd Layer as sigmoid it boosted the performance to beyond 79%.

### Summary

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

#### Summary and Recommendation

  - Overall, by optimizing the model we are able to increase the accuracy to above 79%.
  - This means we are able to correctly classify each of the points in the test data 79% of the time. In other words an applicant has a close to 80% chance of being successful if they have the following:
    - The NAME of the applicant appears more than 5 times (they have applied more than 5 times)
    -  The type of APPLICATION is one of the following: T3, T4, T5, T6 and T19
    - The application has the following values for CLASSIFICATION: C1000, C1200, C2000,C2100 and C3000.

#### Alternative Method

- Although this model worked very well and provided a great deal of accuracy, an alternative approach to recommend is the Random Forest model as it is also suited for classification problems. Using the Random Forest model we can achieve close to 78% accuracy.
