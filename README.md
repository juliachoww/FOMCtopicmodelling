**Introduction**

With current (2023-2024) interest rates standing at 22 year highs, the Federal Reserve's (Fed's) decisons to hold interest rates "higher for longer" or to pivot downwards has gained great scrutiny from analysts and the general public.
As such, a tool that can allow stakeholders to identify main topics about the economic outlook as discussed by the FOMC in their meetings would provide considerable time savings and reduce subjective biases from these stakeholders reading through the wordy minutes themselves.

**Dataset**

The dataset comprises of 121 FOMC meeting minutes documents spanning 15 years from 2009 to 2024.
Specifically, only the "Staff Economic Outlook" section has been identified and extracted for topic modelling purposes.

**Approach**

* The corpus was first pre-processed and tokenized using the NLTK library. Specifically, punctuations and stopwords were removed, the top 10 words identified in the bag of words were removed to improve topic quality, then the words were stemmed to standardize similar words.
* In order to reduce the limitations of the Bag of Words (BoW) method that assigns equal importance to all tokens, I opted to use the TF-IDF vectorization method to better capture the meaning of the FOMC outlook. The advantages of TF-IDF in the specific context of FOMC minutes are twofold: 1) The length of the documents vary greatly from one another and TF-IDF mitigates this by normalizing document length 2) Rare words can be crucial in distinguishing the economic outlook of one document from another and TF-IDF gives tokens with low document frequency a higher weight e.g. covid years are rare in the entire corpus but is an important topic in 2019 and 2020
* The model is then trained using Latent Dirichlet Allocation (LDA), where each FOMC minute "Staff Economic Outlook" section represents a single document in the model.

**Results**
