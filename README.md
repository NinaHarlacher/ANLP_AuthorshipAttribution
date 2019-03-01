# ANLP_AuthorshipAttribution

March 1st, 2019, University of Potsdam

Final project for Advanced Natural Language Processing by Lisa Becker, Nina Harlacher, Joceline Ziegler

Just download all files.

We implemented three models for the attribution of Elizabethan plays to their authors:
- Bag of Words (Word Frequency with Naive Bayes)
- N-gram Tracing (Relative Frequency of ngrams of words/characters)
- Generative Model with Naive Bayes and SVM

The data (classified plays in .txt format) is contained in the EL folder. 

## Bag of Words

    - bagOfWordsLOO.ipynb

Running the notebook creates a file saved in the current directory with a list of plays and their attribution. The overall accuracy is printed.

    - bagOfWordsLOO.ipynb

The file that is created by the notebook containing names of plays and their attribution and the accuracy at the bottom.

## N-gram Tracing

     - n_gram_tracing.ipynb

Implementation of the n-gram tracing approach (Grieve et al. 2018). The very last cell can be changed whether word or character ngrams should be used as well as their order. The accuracy is calculated and printed in the end.

## Generative Model 

    - Generative Model (Sentence as instance + SVM cls).ipynb

Uses each sentence as instance for training data. This approach turned out to be unsuccessful. 
Two data frames are provided, one with features based on two sets of stop words and the other shows the predictions of the model: 

    - DataFrame_SVM.xlsx
    - DataFrame_SVM_Preds.xlsx


    - generative_model.ipynb

compares the results of a generative model using a Naive Bayes classifier or an SVM when using different sets of stop words for feature generation. The initial data frame used is provided as

    - DataFrame.xlsx

and can be read in (rather than running the cell that creates the data frame). Results show when run. The prediction always takes a couple minutes.

    - DataFrame_imp.xlsx

is also provided and contains the data created with a different set of stop words.

Computed accuracies for the classifiers and the stop word sets can be found in the file which is created in the end and provided: 

    - Stopword_results.xlsx 

### Naive Bayes

    - NB_feature_engineering.ipynb

contains the NB generative model by itself as well as the implementation of different features. The function get_features_GM_imp(X_train, X_test) was modified for each feature (the columns of the df accessed, creation of count vectorizers if necessary, stacking the original and added data). Different combinations of features were tested and documented. Adding keywords as a feature improved our model best.
The model is used to attribute two additional plays that are not included in the Fox et al. corpus:
    
    - yorkshire.txt
    - puritan.txt
    

### SVM

    - SVM_feature_engineering.ipynb

Exploring the SVM generative model (though not as thoroughly because it does not seem to perform better than Naive Bayes anyways).

## Results

    - Results.pdf

contains a summary of results of the different models in the form of a table.
