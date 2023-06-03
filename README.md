# Email Sorting Project

Welcome to the Email Sorting Project! Our objective is to develop an efficient algorithm that can classify and sort emails based on their content. To accomplish this, we are employing the advanced "Cross-over CatBoost" algorithm.

## Algorithm Description: Cross-over CatBoost

The "Cross-over CatBoost" algorithm leverages two feature spaces that represent values of the same variable. We hypothesize that these indicators are cumulative, indicating a progressive accumulation of information. Consequently, for each email, we aggregate the indicators within each feature space to derive the corresponding "target" values.

Here is an overview of the algorithm's workflow:

1. Creation of two feature spaces that provide distinct perspectives on the underlying variable.
2. Computation of "target" values by aggregating the indicators within each feature space for every email.
3. Division of the data into training and testing sets to ensure unbiased evaluation.
4. Training of classifiers using one feature space to predict the "target" values from the other feature space.
5. Repetition of step 4, swapping the feature spaces.
6. Evaluation of classifier performance on the testing set for each combination of feature spaces.
7. Analysis of results and selection of the optimal combination of feature spaces.

## Project Description

Let's delve into the details of our email sorting project:

1. Data preprocessing and feature engineering are performed to enhance the quality of the data.
2. "Target" values are calculated by aggregating indicators within each feature space for each email.
3. The dataset is split into training and testing sets to facilitate unbiased evaluation.
4. Multiple classifiers are trained using the "Cross-over CatBoost" algorithm, alternating the feature spaces during training.
5. The performance of the trained classifiers is evaluated on the testing set.
6. The results are analyzed to identify the most effective combination of feature spaces.
7. Finally, the selected classifier is applied to classify and sort new incoming emails.

The Email Sorting Project aims to streamline email organization and categorization, ultimately improving productivity. Say goodbye to email chaos and let's get started!
