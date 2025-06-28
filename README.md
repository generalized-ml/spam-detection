- I solved the problem of spam deetection just for fun.
- Data used - https://spamassassin.apache.org/old/publiccorpus/
 ** Details about the data **
   - Total count: 6047 messages, with about a 31% spam ratio.
     - spam: 500 spam messages, all received from non-spam-trap sources.
     - easy_ham: 2500 non-spam messages.  These are typically quite easy to
        differentiate from spam, since they frequently do not contain any spammish
        signatures (like HTML etc).
    - hard_ham: 250 non-spam messages which are closer in many respects to
        typical spam: use of HTML, unusual HTML markup, coloured text,
        "spammish-sounding" phrases etc.
    - easy_ham_2: 1400 non-spam messages.  A more recent addition to the set.
    - spam_2: 1397 spam messages.  Again, more recent.
 
**Target**

- Preprocess the data
- EDA of the data
- split the data to train test 
- Decide the evaluation metric
- Decide the bunch of models to try
- Go ahead with a model
- Train and report the final evaluatin metric


**Findings**

- Random Forest has a great precision but have poor recall because tree based method will not get a chance to explore the sparse space untill unless there are 10000s of random trees with a good depth
- Best classifier is XGboost with lasso with following preformance - <br>
                                  ## Confusion Matrix

                  |                      | **Predicted Ham** | **Predicted Spam** |
                  |----------------------|-------------------|--------------------|
                  | **Actual Ham**       | 714               | 21                 |
                  | **Actual Spam**      | 9                 | 291                |

                  ### Performance Metrics
                  - **Accuracy**: 0.9710
                  - **Precision**: 0.9327
                  - **Recall**: 0.9700
                  - **F1 Score**: 0.9510

- Next Best classifier is logistic regression with lasso with following preformance - <br>
                                  ## Confusion Matrix

                |                      | Predicted Ham | Predicted Spam |
                |----------------------|---------------|----------------|
                | **Actual Ham**       | 710           | 25             |
                | **Actual Spam**      | 13            | 287            |

                ### Performance Metrics
                - **Accuracy**: 0.9633
                - **Precision**: 0.9199
                - **Recall**: 0.9567
                - **F1 Score**: 0.9379

- I have also used PCA with 45% varuance explained, which was giving this result - <br>
            Explained variance ratio by PCA: 0.4522770080954638<br>
                              ## Confusion Matrix

        |                      | Predicted Ham | Predicted Spam |
        |----------------------|---------------|----------------|
        | **Actual Ham**       | 713           | 22             |
        | **Actual Spam**      | 27            | 273            |

        ### Performance Metrics
        - **Accuracy**: 0.9527
        - **Precision**: 0.9254
        - **Recall**: 0.9100
        - **F1 Score**: 0.9176

