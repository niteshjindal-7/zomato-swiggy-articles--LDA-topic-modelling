# zomato-swiggy-articles--LDA-topic-modelling

This discussion explains the LDA modelling executed on the scrapped data of Zomato and Swiggy food aggregator articles from the ndtv.gadgets website. On the scrapped data, below steps are performed in the notebook-

1. Read Scrapped Article files. Scrapped Articles can be found at:-
https://drive.google.com/drive/folders/1kQ9ikoqa8upS55tvfencPZ5_oUCKtuB_?usp=sharing

2. Filter the scrapped data to get before incidence, during incidence and after incidence data subsets-

     * Zomato_data_during_incidence
     * Zomato_data_after_incidence
     * Zomato_data_before_incidence
     * Swiggy_data_during_incidence
     * Swiggy_data_after_incidence
     * Swiggy_data_before_incidence


    
3. Extract Article content for topic modelling

4. Use WordNet Lemmatizer to lemmatize documents

5. User Named Entity Recognition from Spacy Module to filter out the nonessential entities (for ex-ORG (organization names))

6. Text Cleaning of Articles data

7. Word Tokenization in corpus

8. Create Dictionary and Corpus which is required as an input for LDA modelling

9. Build LDA model selecting K=5 topics: A topic model is a sort of probabilistic generative model to find the representative topic of a document/corpus, which in our case are the documents in the articles. Using the Latent Dirichlet allocation (LDA) technique, we get each the documents in the articles mapped to all of the five topics with certain probability distribution. We are taking number of topics as K=5 in this exercise.

10. Use the gensim model function which trains the LDA model and get the gamma matrix output-
  * Output1 gives the number of topics which best defines a particular document. For example, document1 in the Zomato_data_after_incidence articles appears in four topics sharing     some proportion in each of the four topic. The output matrix contains columns as topic numbers, rows as each document and value as the proportion/percentage value which           a document share within each topic.
        
  * Output2 gives us the dominant topic by finding the topic that share maximum percentage of a document among the selected topics. That is to say, some documents are associated       with multiple topics and have certain contribution in them and the output here givess the topic to which document is most associated with. The output contains features,      
    namely, Doc_num, Dominant_Topic, Perc_Contribution, Topic_Keywords, orig_contents.

Output files as per point #10 can be found at: 
https://drive.google.com/drive/folders/1HMrgInnud8tbd1yNRGj9Tg5jyow67qYl?usp=sharing 


Thats all. By this way, we get to know which document is mapped to which topic and then topics can be clustered and named based on the words having semantic resemblance.
    
    
References:

https://radimrehurek.com/gensim/models/ldamodel.html

https://spacy.io/usage/models

https://www.mdpi.com/2073-8994/11/12/1486/htm
