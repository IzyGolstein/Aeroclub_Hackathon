# Email Sorting Project

During the hackathon, we aimed to create an unsupervised learning algorithm for email sorting without labels. We explored several ideas, including creating our own labels, using neural networks to extract key information from the text, and developing new methods. After preprocessing the text data, we attempted to use unsupervised learning techniques such as clustering on word embeddings. 

<p align="center">
  <strong></strong>
  <br> <!-- Пробел между текстом и фотографией -->
  <img src="https://github.com/IzyGolstein/Aeroclub_Hackathon/assets/112851618/e901f551-7dc5-4b7c-a319-e8f651a24ed8" alt="Sublime's custom image" />
</p>

<div style="padding: 10px;">
  <p style="text-align:left;"><strong>
However, we encountered difficulties as the elbow rule did not work as expected. The point is that percentage decrease is less than 10% after one cluster adding.
</strong></p>
</div>
  
<p align="center">
  <strong></strong>
  <br> <!-- Пробел между текстом и фотографией -->
  <img src="https://github.com/IzyGolstein/Aeroclub_Hackathon/assets/112851618/602d334b-0c57-4dba-92c0-a8f03fb76f76" alt="Sublime's custom image" />
</p>



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
2. We used Word2Vec and self-adding bag-of-words to get embeddings of words.
3. Realisation of "Cross-over CatBoost" algorithm.
4. Making prediction.


## Conclusion 

As a result, we conducted an evaluation of the CatBoost algorithm using cross-validation techniques. We were provided with 500 labeled emails by the organizers to assess the performance of our models. The following results were obtained, which will be presented and analyzed in this section:

![classification_metrics](https://github.com/IzyGolstein/Aeroclub_Hackathon/assets/112851618/7271152c-4854-4ebd-b201-83ff11b7d193)

It is important to acknowledge that certain parts of the algorithm did not perform well. Specifically, the classifier built on the self-adding bag-of-words approach showed suboptimal results. The self-adding bag-of-words method involves creating a bag of words by identifying the most frequent words in texts. It further augments this bag by adding words that have a counter greater than 7, considering that we already have enough words from the initial bag. However, after several iterations of feature augmentation, the quality of the classifier actually decreased.

On the other hand, the classifier based on Word2Vec, a word embedding technique, performed remarkably well. Word2Vec represents words as vectors in a high-dimensional space, capturing semantic relationships between words. Interestingly, when combined with the self-adding bag-of-words approach, the performance of the Word2Vec-based classifier even showed improvement.

Based on these findings, we can conclude that a more well-developed attribute space, such as the one captured by Word2Vec, tends to yield better performance when utilizing the CatBoost algorithm. Conversely, a less refined attribute space, as exemplified by the self-adding bag-of-words method, may lead to a decline in performance.

This observation highlights the significance of feature engineering and selection in the overall success of the CatBoost algorithm. Future iterations of the model should focus on refining the feature space and exploring alternative approaches to feature representation.
