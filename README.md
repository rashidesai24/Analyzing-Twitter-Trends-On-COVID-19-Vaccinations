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


<b> <h5> BACKGROUND </h5> </b> <br>
The COVID-19 pandemic has killed 3.2 million people and infected 150 million around the world as of April 30, 2021. Growing human rights concerns, vaccine movements, and skepticism towards the vaccines, its effects and efficacy have resulted in a multitude of conversations on social media and the process of vaccination becoming a complicated task. No major studies have been conducted to analyze people’s perception of COVID-19 vaccines on social media for the year 2021

<b> <h5> OBJECTIVE </h5> </b> <br>
<li> To extract information from tweets (between January and March, 2021) related to COVID vaccine where opinions are highly unstructured, heterogeneous and are either positive or negative, or neutral and identify driving factors for the change in sentiments </li> 
<li> To explore conversations and abstract "topics" that occur in the collected tweets using topic modeling and text analytics backed by breakthrough events in the timeline </li> 
<li> To visualize the trends in sentiments of Twitter users and popularity associated with the discovered topics </li> 


<b> <h5> DATA PRE-PROCESSING </h5></b> <br> <br>

<b> Data Cleaning </b> <br>

<li> Removed punctuation using remove_punct function with library re </li> 
<li> Removed URLs and emojis in Tokenization using library re </li> 
<li> Removed stopwords using nltk </li> 
<li> Lemmatization of Tweets using nltk.WordNetLemmatizer() </li> <br> 

<b> Individual vs Organizational Tweets </b> <br>
<li> Created a Bag-of-Words with ~175 keywords to filter on Display Names </li> 
<li> Removed 22% of the data </li> 
<li> 2,109,427 tweets remain after removing organizational accounts </li> 
<li> Assigned week numbers (1 to 12) to the dataset </li> 
