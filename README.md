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
 
**Target **
- Preprocess the data
- EDA of the data
- split the data to train test 
- Decide the evaluation metric
- Decide the bunch of models to try
- Go ahead with a model
- Train and report the final evaluatin metric


**Findings**
- 
