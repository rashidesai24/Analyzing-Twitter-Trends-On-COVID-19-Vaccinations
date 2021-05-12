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
<li> Challenges and Future Work </li>

<hr>

<b> <h3> BACKGROUND </h3> </b> 
The COVID-19 pandemic has killed 3.2 million people and infected 150 million around the world as of April 30, 2021. Growing human rights concerns, vaccine movements, and skepticism towards the vaccines, its effects and efficacy have resulted in a multitude of conversations on social media and the process of vaccination becoming a complicated task. No major studies have been conducted to analyze people’s perception of COVID-19 vaccines on social media for the year 2021

<hr>
 <h3> OBJECTIVE </h3>
<li> To extract information from tweets (between January and March, 2021) related to COVID vaccine where opinions are highly unstructured, heterogeneous and are either positive or negative, or neutral and identify driving factors for the change in sentiments </li> 
<li> To explore conversations and abstract "topics" that occur in the collected tweets using topic modeling and text analytics backed by breakthrough events in the timeline </li> 
<li> To visualize the trends in sentiments of Twitter users and popularity associated with the discovered topics </li> 

<hr> 

<h3> TOOLS AND PACKAGES </h3><br>

<table style="width:100%">
  <tr>
    <th>Task</th>
    <th>Technique</th> 
    <th>Tools/Packages Used</th>
  </tr>
  <tr>
    <td>Data Collection</td>
    <td>Tweet extraction from Twitter </td> 
    <td>snscrape</td>
  </tr>
  <tr>
    <td>Data Pre-processing</td>
    <td>Removed punctuation, stopwords, URLs, emojis, lemmatization</td> 
    <td>re, nltk,CountVectorizer, pandas, numpy</td>
  </tr>
  <tr>
    <td>Data Modeling</td>
    <td>Unsupervised LDA</td> 
    <td>pyLDAvis.sklearn, LatentDirichletAllocation, sklearn </td>
  </tr>
  <tr>
    <td>Text Analytics</td>
    <td>Topic Modeling, Sentiment analysis</td> 
    <td>vaderSentiment, corextopic</td>
  </tr>
  <tr>
    <td>Data Visualization</td>
    <td>Multi-attribute plots</td> 
    <td>matplotlib, seaborn, Tableau, wordcloud</td>
  </tr>
  <tr>
    <td>Environments & Platforms</td>
    <td> </td> 
    <td>MS Excel, Google Colab, Jupyter Notebook, Twitter</td>
  </tr>
</table><br>

<hr>
<h3> DATA COLLECTION </h3> 

<table style="width:100%">
  <tr>
    <th>Method</th>
    <th>Notes</th> 
  </tr>
  <tr>
    <td>Tweepy</td>
    <td>3200 tweets; no historical data</td> 
  </tr>
  <tr>
    <td>GetOldTweets3</td>
    <td>Twitter has removed the endpoint the GetOldTweets3 uses </td> 
  </tr>
  <tr>
    <td>TWINT</td>
    <td>Twitter throws a more strict device + IP-ban after a certain amount of queries</td> 
  </tr>
  <tr>
    <td><b>snscrape</b></td>
    <td><b>Scrapped 100K tweets - 96,641 English tweets</b></td> 
  </tr>
  <tr>
    <td>Octoparse (software)</td>
    <td>Very time consuming with the event loop</td> 
  </tr>
</table>

<h4> Data Collection: Identifying COVID-19 Vaccines Content </h4>

<li> Package used: snscrape</li>
<li>Language: English</li>
<li>Keywords: covid vaccine</li>
<li>Timeframe: January 1, 2021 to March 31, 2021</li>
<li>Number of tweets collected = 2.74 million</li>
<li>January - 884,011 tweets | February - 800,008 tweets | March - 1,127,854 tweets</li>
<li>No null values identified</li>

<h4> Data Coverage: </h4> With covid vaccine as the search terms, we believe that our set of keywords provides reasonable coverage and is representative of tweets communicating about COVID-19 vaccines <br>
Individual tweets = 2.1 million <br>
Organizational tweets = 0.59 million <br>

<hr>

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

<hr>
<b> <h3> DATA MODELING </b> </h3>

<h4> Unsupervised LDA </h4>
To understand the abstract topics hidden in the tweets unsupervised LDA technique was implemented using the library 'pyLDAvis'. We discovered 18 different topics considering the cluster size and no overlapping amongst the clusters
<h4> Sentiment Analysis </h4>
Sentiment analysis is a supervised machine learning problem with different types of analysis. We considered a fine-grained sentiment classification with five levels of sentiments - overly positive, positive, neutral, negative, and overly negative. We used VADER (Valence Aware Dictionary for Sentiment Reasoning) as a rule-based model to examine the impact of COVID-19 vaccine on the attitude of Twitter users during the pandemic. 
<h4> CorEx </h4>
Correlation Explanation (CorEx) provides a flexible framework for learning topics that are maximally informative about a corpus of text. Through anchor words, we seeded and guided the topic model towards topics of substantive interest, which allowed us to interact with and refine topics in a way that is not possible with traditional topic models. Normalized Topic Correlation (NTC) represents the correlations within an individual document explained by a particular topic. 

<hr>

<h3> DATA VISUALIZATION </h3> 

<img src="https://github.com/rashidesai24/Analyzing-Twitter-Trends-On-COVID-19-Vaccinations/blob/main/Images/Unsupervised%20LDA.png" alt="alternatetext"> 



<hr>

<h3> RESULTS </h3> 
<li> Discovered 13 unique topics from the tweets across 12 weeks from Jan’21 to Mar’21 </li>
<li>February had the lowest number of tweets (594,050) as compared to January (695,890) and March (819,487) about COVID vaccinations</li>
<li>Positive sentiment contributed the most in overall sentiments of Twitter users (732,395), followed by neutral (579,493) and negative (525,866) sentiments</li>
<li>People were discussing the most about topics like Vaccination status, Travel, Pandemic, Politics, Vaccine Approval</li>
<li>Topics that remained underrepresented were People Against Vaccine, Political and COVID leaders, Who Got Vaccinated</li>

<hr>

<h3> CONCLUSION </h3>
This study focused on demonstrating the conversations around COVID-19 vaccines on Twitter using a dataset created with tweets from individuals leveraging Machine Learning and Text Analytics approach. We performed exploratory data analysis using Unsupervised LDA to identify initial implicit topics. The dataset was further analysed for positive and negative sentiments. We further performed topic modeling for a deeper understanding of topics and their popularity across time. 

<hr>

<h3> REFERENCES </h3>
<li> Praveen SV, Ittamalla R, Deepak G. Analyzing the attitude of Indian citizens towards COVID-19 vaccine - A text analytics study. Diabetes Metab Syndr. 2021 Mar-Apr;15(2):595-599. doi: 10.1016/j.dsx.2021.02.031. Epub 2021 Feb 27. PMID: 33714134; PMCID: PMC7910132 </li>
<li> DeVerna, M., Pierri, F., Truong, B., Bollenbacher, J., Axelrod, D., Loynes, N., . . . Bryden, J. (2021, April 20). CoVaxxy: A collection of ENGLISH-LANGUAGE Twitter posts About COVID-19 Vaccines </li>
<li> K. Hazel Kwon, J. Hunter Priniski & Monica Chadha (2018): Disentangling User Samples: A Supervised Machine Learning Approach to Proxy-population Mismatch in Twitter Research, Communication Methods and Measures, DOI: 10.1080/19312458.2018.1430755 </li>
<li> Scraping Tweets with snscrape - https://betterprogramming.pub/how-to-scrape-tweets-with-snscrape-90124ed006af </li>
<li> Vader Sentiment Analysis - 
https://github.com/cjhutto/vaderSentiment </li>
<li> Unsupervised LDA - 
https://www.kaggle.com/keitazoumana/topic-modeling-with-lda </li>

<hr>

<h3> CHALLENGES AND FUTURE WORK </h3>
<b> Challenges </b>: Identifying package for tweet scraping and recognizing limitations on extraction, large execution times and runtime errors due to memory limitation for parts of data modeling </li>
<h4> Future Work </h4>
<li> Low impact insights from VADER Sentiment Analysis opens up a scope for deep dive into topics independently like People For/Against vaccines </li>
<li> Explore conversations and sentiments in organizational tweets </li>
<li> Number of active COVID cases, recoveries and deaths for the three months </li>
