# Email Sorting Project

During the hackathon, we aimed to create an unsupervised learning algorithm for email sorting without labels. We explored several ideas, including creating our own labels, using neural networks to extract key information from the text, and developing new methods. After preprocessing the text data, we attempted to use unsupervised learning techniques such as clustering on word embeddings. 


<div style="display: flex; justify-content: space-around;>
  <div style="padding: 10px;">
    <p align="center"><strong></strong></p>
    <img src="https://github.com/IzyGolstein/Aeroclub_Hackathon/assets/112851618/e901f551-7dc5-4b7c-a319-e8f651a24ed8" alt="drawing" width="500" />
  </div>
  <div style="padding: 10px;">
    <p align="center"><strong></strong></p>
    <img src="https://github.com/IzyGolstein/Aeroclub_Hackathon/assets/112851618/602d334b-0c57-4dba-92c0-a8f03fb76f76" alt="drawing" width="500" />
  </div>
</div>



However, we encountered difficulties as the elbow rule did not work as expected. 


As a result, we decided to use simple vectorization and bag-of-words techniques for classification. After completing this step, we faced the challenge of combining these two algorithms. Our solution was to leverage two feature spaces that represent values of the same variable and aggregate the indicators within each feature space for every email.

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

1. We created features - presence of reservation number, number of words - personal data, trimmed letters, highlighting key pieces, classical lemmitization, stop-words etc.
2. We used Word2Vec to get embeddings of words.
3. Realisation of "Cross-over CatBoost" algorithm.
4. Making prediction.
