# Email Sorting Project

_Welcome to the Email Sorting Project! Our objective is to develop an efficient algorithm that can classify and sort emails based on their content(availability/absence of application). To accomplish this, we are employing the advanced "Cross-over CatBoost" algorithm._

## Algorithm Description: Cross-over CatBoost

The "Cross-over CatBoost" algorithm leverages two feature spaces that represent values of the same variable. We hypothesize that these indicators are cumulative, indicating a progressive accumulation of information. Consequently, for each email, we aggregate the indicators within each feature space to derive the corresponding "target" values.

_Here is an overview of the algorithm's workflow:_

1. Creation of two feature spaces that provide distinct perspectives on the underlying variable.
2. Computation of "target" values by aggregating the indicators within each feature space for every email.
3. Division of the data into training and testing sets to ensure unbiased evaluation.
4. Training of classifiers using one feature space to predict the "target" values from the other feature space.
5. Repetition of step 4, swapping the feature spaces.
6. Evaluation of classifier performance on the testing set for each combination of feature spaces.
7. Analysis of results and selection of the optimal combination of feature spaces.

## Project Description

_Let's delve into the details of our email sorting project:_

1. We created features - presence of reservation number, number of words - personal data, trimmed letters, highlighting key pieces, classical lemmitization, stop-words etc. 
2. We used Word2Vec to get embeddings of words. 
3. Realisation of "Cross-over CatBoost" algorithm.
4. Making prediction.


The Email Sorting Project aims to streamline email organization and categorization, ultimately improving productivity. Say goodbye to email chaos and let's get started!
