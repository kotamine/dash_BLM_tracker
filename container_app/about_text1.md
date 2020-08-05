
## About this app

This site is a web application of **Twitter** data gathering, storage, and analysis on hashtag **BlackLivesMatter**. It is powered by **Twitter API**, **AWS Kinesis**, **Python**, and **Dash**. [Source code](link_here). 

Users of this app can **browse through BLM statistics** for **selected city and time** to observe **trends in sentiments and emotions** and discover **top tweets and influencers**. One can also apply **a keyword filter** to narrow the focus.   



### Current Project Status 

The app currently mostly uses **the data collected during the development stage**. There have been some disruptions in the data collection process, so **the data are quite incomplete for some dates and hours.**  

More complete data can be incorporated once the data archives are collected and organized (work in progress).  


---

### App Components

#### Dataset Selection

The app initially loads summary statistics of data for **all cities**.  **All cities** data are based on **a 2% random sample** of the whole data collected, and hence the app lets you choose a version of the random sample. When you **select a particular city**, the app loads a pre-processed dataset filtered by the city's name in tweet text.  

Initially, the date and time are set at the current time in CST. When you **select a date**, the app loads archival data, recalculate summary statistics, and updates figures and tables. When you **select an hour**, the app updates statistics for the last hour under the Top Words, Top Tweets, and Top Users tabs.  

You can further **filter data by entering a filtering keyword**. The app will go back to the archival raw data, apply the filter in tweet text, and recaulculate statistics, which involves somewhat intensive data processing and hence takes time. Filtering can be used to target your search. Note that depending on the size of the dataset, filtering may result in much fewer data points or no data at all. 


#### Sentiments

**Sentiment** score is calculated for each tweet by the "polarity_scores" of the **nltk** package (Natural Language Toolkit), ranging from -1 (negative) to +1 (positive) sentiment. The relevant tweets' scores are then averaged for each hour. 

**Emotions** are calculated for each tweet by the top emotions the **nrclex** package (NRC Lexicon). Each tweet is assessed for exhibiting which of the 7 selected emotions and index for 0 (absent of a given emotion) or 1 (present). Multiple emotions are indexed 1 in the case of a tie. The relevant tweets' indices are averaged for each hour.   


#### Top Words

The app calculates the **most frequently occuring words** for a selected dataset and displays them as word cloud and bar chart.  If the selected dataset is large, the app uses a random sample of 10,000 tweets, 



#### Top Tweets

The app identifies **the most retweeted tweets** in **a selected timespan** (out of last hour, today, yesterday, past 7 days). 


#### Top Users


The app identifies **the most retweeted Twitter users** in **a selected timespan** (out of last hour, today, yesterday, past 7 days). 



--- 
### Data Collection and Processing
#### Data Flow Chart