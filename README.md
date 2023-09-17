# deep-learning-challenge
Challenge 21

## Purpose
This analysis seeks to use the historical data of a nonprofit foundation called Alphabet Soup, which has funded the ventures of more than 34,000 organizations, to predict which future ventures will be successful.  We employed machine learning and neural networks to help Alphabet Soup select the applicants with the best chance of success.  We had access to, and evaluated features such as Affiliated sector of industry, Government organization classification, Use case for funding, Organization type, Active status, Income classification, Special considerations for application, Funding amount requested, and whether the money was used effectively. 

## Results
Using bulleted lists and images to support your answers, address the following questions:

**Data Preprocessing**
Dependent Variable (target): 
  - IS_SUCCESSFUL
Independent Variables (features): 
  - APPLICATION_TYPE
  - AFFILIATION
  - CLASSIFICATION
  - USE_CASE
  - ORGANIZATION	
  - STATUS
  - INCOME_AMT
  - SPECIAL_CONSIDERATIONS
  - ASK_AMT
Irrelevant Variables (do not influence success):
  - EIN
  - NAME

![image](https://github.com/JessicaRBailey/deep-learning-challenge/assets/129994268/084eaf34-1a98-441e-b916-789aa14fe072)


**Compiling, Training, and Evaluating the Model**
The following modifications were used in the attempt to increase model performance:
  - Layers: Initially, three layers were used, an input, 1 hidden, and an output.  The number of layers was increased in subsequent attempts to optimize.  The final attempt included 5 layers: 1 input, 3 hidden, and 1 output. 
  - Neurons: Initially, 6 neurons were used in the input and hidden layers, and one neuron in the output layer, for a total params = 313.  Neurons were increased in subsequenet attempts until a final attempt with 32 in the input layer, 16, 8, and 4 in the three hidden layers, and 1 in the output layer, for total params = 2049.
  - Activation functions:  Initially, two activation functions were used, relu for input and hidden, and sigmoid for output.  In the final attempt, the tanh activation function was used in the third hiddent layer. 
  - Epochs: One attempt was made to increase epochs to 1000 to see if allowing additional trials would increase model performance, but the results were the same.  All attempts seemed to stabilize no later than the 10th epoch, so we reduced the epochs to 50 in later attempts in order to save time and resources.
The decisions to increase layers, neurons, and activation functions were reached after changing the features and early increases of layers and neurons did not lead to increases in accuracy of the model.

![image](https://github.com/JessicaRBailey/deep-learning-challenge/assets/129994268/780b32b1-3efd-4a53-9503-65caaa563e16)

Ultimately, we were not able to achieve the target model performance of 75% accuracy.  We did note that AFFILIATION is a key feature.  Without AFFILIATION, the loss increases to .63 and the accuracy decreases to .63.  No other modifications had any significant effect on the model.

- Original Attempt:  Loss: 0.554374098777771, Accuracy: 0.72967928647995
- Optimization Attempt #1:  Loss: 0.5560629963874817, Accuracy: 0.7274635434150696
- Optimization Attempt #2:  Loss: 0.5528214573860168, Accuracy: 0.7282798886299133
- Optimization Attempt #3:  Loss: 0.5623424649238586, Accuracy: 0.7268804907798767
- Attempt #3 w/o 'AFFILIATION':  Loss: 0.6336261630058289, Accuracy: 0.6261224746704102

## Summary
Ultimately, as long as the AFFILIATION feature was included in the analysis, all models achieved approximately a loss of .55 - .56 and an accuracy of .72 - .73.  The best model was the second attempt and that model was saved as AlphabetSoupCharity_Optimization.h5.  Because we did not achieve our target of 75% accuracy, it is recommended that a different model could be attempted.  This model used a classification strategy, so perhaps a regression model could provide a linear relationship that could help Alphabet Soup make a decision.  Another option could be to try a clustering analysis that would group previous ventures on similarities that are correlated with success or failure.  If a target performance cannot be reached with other methods, this model does better than chance, allowing a 73% chance of correctly identifying a successful application.  
