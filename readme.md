# Project 3: Web APIs & NLP

--- 
#### 
Shuyi 
---

### Problem Statement


We are Zoom's data science team, addressing our software development and digital marketing teams, looking for solutions to ultimately inprove Zoom's bottomline for the shareholers. Microsoft Teams (MST) is our largest, fastest growing and well funded competitor, we want to examine what users have been discussing on Reddit by applying NLP techniques. 

We will then train a classifier to accurately classify content between the two Sub-Reddits which are Zoom and Microsoft Teams. We will be using the following models of Logistic Regression, Random Forest and Multinomial Naive Bayes, before selecting the best performing model to be refined.

Based on the model, we will make recommendations to the software development team and the marketing team. We evaluate success as the final model being able to provide sufficiently high level of classification accuracy, so that we can extract words or word groupings with high coefficient to either class, and use them SEM & SEM, and explore them to suggest user's pain points or new technical features desired.

For the Software Development Team, we will attempt to highlight what are the common issues faced by users, as well as any additional features that the users would like to have. Hence, we will be able to update the product to retain more current users and attract new users.

For the Digital Marketing Team, we will look at what features the Microsoft Teams (MST) users have issues with (more than Zoom users). We will tweak our campaigns to capitalise on their perceived weaknesses and (ii) to look at which words are closely associated with Zoom and MST. These words can considered for our Search Engine Marketing and Search Engine Optimisation campaigns. To utilise these words as paid keywords such as Google Ads or organic keywords in our sites.

Even though Zoom has the biggest market share of video conferencing platforms at the global start of the pandemic in April 2020, Microsoft has been hitting back hard by converting existing MS Office 365 users to MS Teams. We need to seek and retain more customers before MS gets to them.

### Data

Data points were scrapped from 
1. Zoom subreddit. https://www.reddit.com/r/Zoom/
2. Microsoft Teams subreddit. https://www.reddit.com/r/Zoom/

1.Basic readings related to Zoom vs Teams' market share 

https://www.trustradius.com/buyer-blog/top-5-skype-alternatives

https://www.businessofapps.com/data/zoom-statistics/

https://www.businessofapps.com/data/microsoft-teams-statistics/
    
2.A couple of Quora posts on why the preference for Zoom over other platforms 

https://www.quora.com/Why-is-Zoom-the-more-popular-option-for-video-calls-or-conferencing-for-online-classes-and-not-older-services-like-Skype-or-Google-Hangouts

https://www.quora.com/Why-did-Zoom-video-chat-get-so-popular-Why-dont-people-just-use-existing-video-conferencing-services-like-Google-Hangouts-or-Skype

https://www.quora.com/Why-are-people-using-Zoom-There-is-some-obvious-upside-to-Zoom-over-its-competition-from-Microsoft-s-Skype-and-Google-Hangouts

3.Some Zoom vs Teams comparisons

https://www.forbes.com/advisor/business/software/microsoft-teams-vs-zoom/

https://www.techradar.com/sg/news/microsoft-teams-vs-zoom-which-video-conferencing-and-collaboration-service-is-best

https://www.unifysquare.com/blog/microsoft-teams-vs-zoom/

4.Digital marketing refresher

https://www.k6agency.com/negative-keywords/

https://www.revlocal.com/resources/library/blog/how-to-differentiate-google-ads-and-google-smart-campaigns

https://digitalmarketinginstitute.com/blog/how-do-seo-and-sem-work-together-in-2018


 0   subreddit           15033 non-null  object
 1   text                15033 non-null  object
 2   cleaned             15033 non-null  object
 3   lemmatized          15033 non-null  object
 4   stemmed             15033 non-null  object
 5   target              15033 non-null  int64 
 6   char_count_text     15033 non-null  int64 
 7   char_count_cleaned  15033 non-null  int64 
 8   char_count_lem      15033 non-null  int64 
 9   char_count_stem     15033 non-null  int64 




### Data Dictionary
|Columns|Type|Dataset|Description|
|---|---|---|---|
|**subreddit**|*object*|zoom_team|The Zoom or Microsoft Teams subreddit from which the text originated| 
|**text**|*object*|zoom_team|The title and selftext fields combined into one field|
|**cleaned**|*object*|zoom_team|Text cleaned with Regex| 
|**lemmatized**|*object*|zoom_team|Cleaned text that has been lemmatized|
|**stemmed**|*object*|zoom_team|Cleaned text that has been stemming| 
|**target**|*int64*|zoom_team|'1' for 'Zoom', '0' for 'Microsoft Teams'| 
|**char_count_text**|*int64*|zoom_team|The number of characters in original text|
|**char_count_cleaned**|*int64*|zoom_team|The number of characters in regex cleaned text|
|**char_count_lem**|*int64*|zoom_team|The number of characters in lemmatized text| 
|**char_count_stem**|*int64*|zoom_team|The number of characters in stemmed text| 


### Conclusions
.
Our LogisticRegression model with TfidfVectorizer on Lemmantized data can predict a post's subreddit with 93% accuracy. 

Using the model's coefficients, we identified top words that would result in the model predicting either class.
Every key word will benefit from a deep dive to further establish what the end user needs / struggles with. 

#### Recommendations
For the software devs: At a start, we should be consider prioritizing a Zoom feature that enables certain audio to be played, eg: host's music streaming, audio from websites host is showing etc. Chat which seems to be a pain for teams users, should continue to be easy to use, avoiding the Team's poor UI/UX. 

For the marketing team: The top 20 words for zoom / teams can be incorparated into SEM & SEM strategies. While we are not suppose to use competitors trademark names such as microsoft in the ad body itself, we can buy them as keywords, or better yet, use their technical/UX weakness as words to have potenial users visit our website/ads to convert the users. 

There might be a need to rework the zoom promotion codes giveaways, join & code returned many posts to 'join my zoom discord for promo codes'.

#### Future Work
In terms of future work, we can update the dataset again in Apr 2022 and to compare the difference. 
Create new machine learning models to deep dive into the top words to get... top words of top words. A better overview of what made them the top words.