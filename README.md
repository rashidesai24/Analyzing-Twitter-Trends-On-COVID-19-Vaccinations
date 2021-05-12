# Analyzing-Twitter-Trends-On-COVID-19-Vaccinations
A quantitative study comprising Twitter discussions and thematic analysis for COVID-19 vaccines

<b> <h3> TABLE OF CONTENTS  </h3></b>

<li> Background </li> 
<li> Objective </li> 
<li> Tools and Packages </li> 
<li> Data Collection </li>  
<li> Data Pre-Processing </li> 
<li> Data Modeling </li> 
<li> Data Visualization </li> 
<li> Results </li> 
<li> Conclusion </li> 
<li> References </li> 
<li> Challenges and Future Work </li> <br>


<b> <h3> BACKGROUND </h3> </b> 
The COVID-19 pandemic has killed 3.2 million people and infected 150 million around the world as of April 30, 2021. Growing human rights concerns, vaccine movements, and skepticism towards the vaccines, its effects and efficacy have resulted in a multitude of conversations on social media and the process of vaccination becoming a complicated task. No major studies have been conducted to analyze people’s perception of COVID-19 vaccines on social media for the year 2021

<b> <h3> OBJECTIVE </h3> </b>
<li> To extract information from tweets (between January and March, 2021) related to COVID vaccine where opinions are highly unstructured, heterogeneous and are either positive or negative, or neutral and identify driving factors for the change in sentiments </li> 
<li> To explore conversations and abstract "topics" that occur in the collected tweets using topic modeling and text analytics backed by breakthrough events in the timeline </li> 
<li> To visualize the trends in sentiments of Twitter users and popularity associated with the discovered topics </li> 


<b> <h3> DATA PRE-PROCESSING </h3></b>

<b> Data Cleaning </b> 

<li> Removed punctuation using remove_punct function with library re </li> 
<li> Removed URLs and emojis in Tokenization using library re </li> 
<li> Removed stopwords using nltk </li> 
<li> Lemmatization of Tweets using nltk.WordNetLemmatizer() </li> <br> 

<b> Individual vs Organizational Tweets </b> <br>
<li> Created a Bag-of-Words with ~175 keywords to filter on Display Names </li> 
<li> Removed 22% of the data </li> 
<li> 2,109,427 tweets remain after removing organizational accounts </li> 
<li> Assigned week numbers (1 to 12) to the dataset </li> 


<b> <h3> DATA MODELING </b> </h3>

<h4> Unsupervised LDA </h4>
To understand the abstract topics hidden in the tweets unsupervised LDA technique was implemented using the library 'pyLDAvis'. We discovered 18 different topics considering the cluster size and no overlapping amongst the clusters
<h4> Sentiment Analysis </h4>
Sentiment analysis is a supervised machine learning problem with different types of analysis. We considered a fine-grained sentiment classification with five levels of sentiments - overly positive, positive, neutral, negative, and overly negative. We used VADER (Valence Aware Dictionary for Sentiment Reasoning) as a rule-based model to examine the impact of COVID-19 vaccine on the attitude of Twitter users during the pandemic. 
<h4> CorEx </h4>
Correlation Explanation (CorEx) provides a flexible framework for learning topics that are maximally informative about a corpus of text. Through anchor words, we seeded and guided the topic model towards topics of substantive interest, which allowed us to interact with and refine topics in a way that is not possible with traditional topic models. Normalized Topic Correlation (NTC) represents the correlations within an individual document explained by a particular topic. 

<h3> RESULTS </h3> 
<li> Discovered 13 unique topics from the tweets across 12 weeks from Jan’21 to Mar’21 </li>
<li>February had the lowest number of tweets (594,050) as compared to January (695,890) and March (819,487) about COVID vaccinations</li>
<li>Positive sentiment contributed the most in overall sentiments of Twitter users (732,395), followed by neutral (579,493) and negative (525,866) sentiments</li>
<li>People were discussing the most about topics like Vaccination status, Travel, Pandemic, Politics, Vaccine Approval</li>
<li>Topics that remained underrepresented were People Against Vaccine, Political and COVID leaders, Who Got Vaccinated</li>

<h3> CONCLUSION </h3>
This study focused on demonstrating the conversations around COVID-19 vaccines on Twitter using a dataset created with tweets from individuals leveraging Machine Learning and Text Analytics approach. We performed exploratory data analysis using Unsupervised LDA to identify initial implicit topics. The dataset was further analysed for positive and negative sentiments. We further performed topic modeling for a deeper understanding of topics and their popularity across time. 


<h3> REFERENCES </h3>
<li> Praveen SV, Ittamalla R, Deepak G. Analyzing the attitude of Indian citizens towards COVID-19 vaccine - A text analytics study. Diabetes Metab Syndr. 2021 Mar-Apr;15(2):595-599. doi: 10.1016/j.dsx.2021.02.031. Epub 2021 Feb 27. PMID: 33714134; PMCID: PMC7910132 </li>
<li> DeVerna, M., Pierri, F., Truong, B., Bollenbacher, J., Axelrod, D., Loynes, N., . . . Bryden, J. (2021, April 20). CoVaxxy: A collection of ENGLISH-LANGUAGE Twitter posts About COVID-19 Vaccines </li>
<li> K. Hazel Kwon, J. Hunter Priniski & Monica Chadha (2018): Disentangling User Samples: A Supervised Machine Learning Approach to Proxy-population Mismatch in Twitter Research, Communication Methods and Measures, DOI: 10.1080/19312458.2018.1430755 </li>
<li> Scraping Tweets with snscrape - https://betterprogramming.pub/how-to-scrape-tweets-with-snscrape-90124ed006af </li>
<li> Vader Sentiment Analysis - 
https://github.com/cjhutto/vaderSentiment </li>
<li> Unsupervised LDA - 
https://www.kaggle.com/keitazoumana/topic-modeling-with-lda </li>

<h3> CHALLENGES AND FUTURE WORK </h3>
<b> Challenges </b>: Identifying package for tweet scraping and recognizing limitations on extraction, large execution times and runtime errors due to memory limitation for parts of data modeling </li>
<h4> Future Work </h4>
<li> Low impact insights from VADER Sentiment Analysis opens up a scope for deep dive into topics independently like People For/Against vaccines </li>
<li> Explore conversations and sentiments in organizational tweets </li>
<li> Number of active COVID cases, recoveries and deaths for the three months </li>
