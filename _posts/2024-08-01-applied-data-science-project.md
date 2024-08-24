---
layout: post
author: Kendra
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
The project aims to develop a positive and supportive digital platform to provide emotional support and a sense of community for individuals experiencing loneliness and social isolation. The platform will offer a safe and anonymous space for users to connect, share experiences, and access resources to address their respective challenges.

A significant portion of the population experiences feelings of loneliness and social isolation, often leading to negative mental health outcomes. The r/ForeverAlone community highlights a group of individuals struggling with these challenges. Currently, there is a lack of dedicated online platforms providing comprehensive support and community for this demographic. This project aims to address this gap by developing an online support system that offers emotional support, resources, and a sense of belonging to individuals within the r/ForeverAlone community.

The business objectives of this project are : 
1.	Identify distinct demographic groups within the r/ForeverAlone community to create social marketing strategy to increase public’s interest to join the community.
2.	Uncover the primary topics discussed within the r/ForeverAlone community to gain insights into the specific challenges users face and determine what users hope to achieve through the online community.
3.	Determine the likelihood of depression in users based on their demographic and behavioral attributes
4.	Interpret the predominant emotions and overall sentiment expressed within the r/ForeverAlone community to understand the struggles and motivation of the users.
   
To measure the project's success , we will aim to gather positive sentiment expressed in user posts of at least 20% after the online community has been set up.

As for my part of the project, I will be focusing on business objective 2 to uncover the primary topics discussed within the r/ForeverAlone community.


## Work Accomplished

#### Data Collection 

<img width="534" alt="image" src="https://github.com/user-attachments/assets/c75c9b6a-e0f8-47f0-abae-d08016bc2a0a">

1. Install Required Packages:
-	Install the necessary Python libraries using pip:
-	praw for interacting with the Reddit API
-	pandas for data manipulation and analysis
-	textblob for sentiment analysis (optional)
2. Set Up Reddit App:
•	Create a Reddit app to access the API:
-	App Name: ForeverAloneScraper
-	App ID: RCwwv39rNnATMc1p5nL-DQ
3. Set Up Reddit API Credentials:
-  Create a PRAW Reddit instance using the obtained credentials.
4. Scrape Reddit Posts:
-	Define a function to scrape posts from r/foreveralone using the specified keywords (improve or better).
-	Set search parameters (subreddit, query, limit=1000).
-	Due to the specific keywords,subreddit nature and Reddit API restrictions only 190 posts were available for scraping out of the intended 1000.
-	Iterate through the scraped posts, extracting relevant information (title, post, comments, URL).
-	Store the extracted data in a list.
5. Export to CSV File:
- Define the CSV file name (FA_improve.csv).
- Write the scraped data (post titles, posts, comments, URLs) to the CSV file.

The terms "improve" or "better" might seem limited in scope, but they can indirectly provide insights into the challenges faced by the r/ForeverAlone community and their aspirations.

Users often express their desire for improvement in areas where they perceive shortcomings. For example, posts containing "improve social skills" can indicate challenges in social interaction.

Users seeking to "better" their situation will also reveal their desired outcomes. 

## Data Preparation

### Data Transformation 

![image](https://github.com/user-attachments/assets/9b109744-5078-44f8-96ff-9261269a55c8)

1. Import Necessary Package 
- Pandas: For data manipulation and analysis.
- Matplotlib and Seaborn: For data visualization.
- WordCloud: For creating word clouds.
- Gensim: For natural language processing tasks.
- NLTK: For natural language toolkit, including stop words.
- Downloads the NLTK stopwords for later use.
- Reads the CSV file into a Pandas DataFrame.

2. Check Data Shape, Dtype, and Dataset
- Displays the shape of the DataFrame (number of rows and columns).
- Show the data types of each column.
- Preview of the first few rows of the data.

3. Combine text Columns
- Concatenates the 'title', 'selftext', and 'comments' columns into a new column named 'text'.

4. Drop the original columns 

### Data Preprocessing
![image](https://github.com/user-attachments/assets/b2519eb7-6e6e-4c13-8446-f3573f4354b7)

1. Convert to lowercase, remove URL, punctuation, numbers, and special characters:
- Standardizes the text by converting all characters to lowercase.
- Remove URLs, punctuation, numbers, and special characters that can introduce noise and hinder the analysis.
  
2. Ensure no NaN values, tokenize:
- Check  for missing values (NaN) in the text data and replaces them with empty strings.
- Tokenization splits the text into individual words or tokens.
  
3. Remove stop words, lemmatize and stem:
- Stop words are common words that carry little meaning in text analysis and are removed.
- Lemmatization reduces words to their root form.
- Stemming chops off word endings.
  
4. TF-IDF:
- TF-IDF stands for Term Frequency-Inverse Document Frequency.
- It assigns weights to words based on their frequency within a document and across the entire dataset.
- Words that appear frequently in a document but rarely in others have higher TF-IDF scores.

### Data Exploration 

![image](https://github.com/user-attachments/assets/d414defb-d54a-4495-b390-a0b9f1398de5)


 The word cloud was generated using TF-IDF weighting, which emphasizes words with high frequency within specific posts but lower overall frequency within the dataset.

 The word cloud reveals several prominent themes: 

1. Relationship and Social Connection:

The words "relationship," "social," "friend," "partner," and "date." are central to the word cloud, emphasizing the core experience of community members. This suggest a a strong desire for relationships, companionship, and social connection. 

2. Self-esteem and low confidence:

Words such as "worth," "confidence," and "attractiveness." could indicate users are struggling with low self-esteem and negative self-image.

3. Emotional Struggles:

Words like "lonely," "sad," "depressed," and "pain." highlight users are grappling with a range of emotional challenges, including loneliness, sadness, depression, and anxiety.

4. Seeking Support and Advice:

Users are actively seeking guidance and support to navigate their challenges. The words "help," "advice," and "support." indicate a desire for guidance and understanding from the community.

5. Negative Experiences:
   
A significant number of users have experienced negative experiences in relationships or social interactions. This is suggested by terms like "reject," "hurt," and "wrong."

![image](https://github.com/user-attachments/assets/e2e76666-aa73-4bb8-afe3-a24e5f7de392)


The term frequency graph was generated using TF-IDF weighting, this shows the top 20 most common words in the dataset. 

Some key observation from the graph include : 

1. High Frequency of Terms related to Relationship and Social Connection: Words like "friend," "someone," "never," "woman," and "relationship." dominate the graph. This indicates a strong desire for relationships, companionship, and social connection.

2. Emphasis on Emotional Struggles: Terms like "alone," "mean," "live," and "give." suggest that users are grappling with feelings of loneliness, rejection, and depression.

3. Search for Solutions:  Users are actively seeking guidance and support to navigate their challenges. This is indicated by terms like "help," "talk," and "always."

4. Self-Esteem and Confidence : While less prominent than the previous themes, there is some evidence of concerns about self-esteem and confidence. This is suggested by terms like "attract" and "girl."


### Modelling
To uncover the underlying latent topics within the dataset, Latent Dirichlet Allocation (LDA) will be employed to identify the primary themes or topics discussed by users. To find the most suitable number of topics, coherence scores and perplexity scores are calculated for different numbers of topics.

![image](https://github.com/user-attachments/assets/4b44c0f0-5ca5-48a4-94ae-d876d75b1822)
The coherence graph reaches a peak at around 10 topics. This indicates that a model with 10 topics provides the highest coherence score, suggesting it effectively captures the latent themes in the data. Beyond 10 topics, the coherence score starts to decrease. This suggests that adding more topics might lead to overfitting or less meaningful topic interpretations.

![image](https://github.com/user-attachments/assets/6d1d5b6d-84ab-4465-b39b-0fa6c6f59b77)
The perpelxity graph reaches a plateau around 8-10 topics. This suggests that adding more topics beyond this point doesn't significantly improve the model's fit.After the plateau, the perplexity score starts to increase slightly. This might indicate that adding too many topics could lead to overfitting or less meaningful topic interpretations.

Based on the coherence and perplexity graphs, choosing 6 topics for the LDA model is a reasonable decision, especially given the relatively small dataset of 190 documents. While the coherence score continues to increase slightly beyond 6 topics, the improvement may not be substantial enough to warrant the additional complexity. The perplexity score plateaus around 8-10 topics, but there's a relatively small difference between the perplexity scores for 6 and 10 topics. With fewer topics, the results may be easier to interpret and understand.


### Evaluation

<img width="448" alt="image" src="https://github.com/user-attachments/assets/c85bbcd2-83fd-4341-ac7c-6fad2e07c4e0">

To set the parameters for the LDA model , numeber of topics was set to 6 while number of top words to display for each topic was set to 10. The number of passess over the dataset during training was set at 20 passes. 

The follwing can be observed in the LDA model topics : 

1. Topic 0 :
- Keywords: "unwant", "help", "alcohol", "hate", "take", "week", "someth", "food", "least", "social"
- No. of documents associated with Topic : 30
- Interpretation : This topic appears to focus on negative emotions, self-harm, and social isolation. The keywords suggest feelings of unwantedness, seeking help, substance abuse, and difficulty connecting with others.

2. Topic 1:
- Keywords: "woman", "ugli", "live", "attract", "averag", "citi", "find", "plan", "wrong", "someth"
- No. of documents associated with Topic : 32
- Interpretation: This topic seems to revolve around self-esteem, and dating difficulties. The keywords suggest concerns about appearance, and having difficulties to attract a partner.

3. Topic 2:
- Keywords: "love", "attract", "never", "someon", "someth", "live", "friend", "happi", "fuck", "take"
- No. of documents associated with Topic : 46
- Interpretation: This topic is likely related to relationships, love, and desire. The keywords suggest a focus on finding love, attraction, and the challenges and complexities of relationships.

4. Topic 3:
- Keywords: "blood", "woman", "someon", "friend", "virgin", "date", "take", "mean", "never", "donat"
-  No. of documents associated with Topic : 52
-  Interpretation: This topic seems to be about social interactions, relationships, and potentially sensitive topics like  personal experiences with virginity, societal expectations surrounding it and experiences of never having had sex.  It's possible that the term "blood" is a misclassification where the LDA model might have misinterpreted the context in which "blood" was used. 

5. Topic 4 : 
-  Keywords: "friend", "never", "girl", "someon", "social", "woman", "attract", "date", "find", "relationship"
-  No. of documents associated with Topic : 149
-  This topic is likely related to relationships, friendships, and challenges faced in social interactions. The keywords suggest discussions about friendships, dating, and difficulties finding social connections.

6. Topic 5:
- Keywords: "relationship", "someon", "love", "woman", "never", "cheat", "alon", "friend", "famili", "happi"
- No. of documents associated with Topic : 73
- This topic appears to focus on relationships, love, and family. The keywords suggest discussions about relationships, love, family dynamics, and happiness.

The significantly higher number of documents associated with Topic 4, with 149 related documents, compared to the other topics suggests that this topic is the most prevalent within the dataset. This indicates that a large portion of the discussions within the r/ForeverAlone community revolves around the themes associated with Topic 4.

The uneven distribution of documents across the topics highlights that some themes are more prevalent than others. This indicates that certain topics are of greater interest or concern to users within the community.

<img width="397" alt="image" src="https://github.com/user-attachments/assets/f13e927f-e22a-49c6-9816-9e602a404474">

As observed in the intertopic map above, we could infer that : 
- Topic 3 and 4 appear to be closely related, as indicated by their proximity on the map. This suggests that discussions related to these topics often overlap or share common themes.
- Topic 1 and 2 seems to also have some overlap. This suggests that discussions related to these topics might occasionally intersect.
- Topic 5 and 6 appears to be relatively distant from the other topics, suggesting that it represents a distinct theme or set of discussions.
- The size of the circle representing Topic 1 is the largest in in the intertopic map indicates that Topic 1 is the most prevalent topic within the dataset, suggesting that a significant portion of the discussions within the r/ForeverAlone community revolve around the themes associated with this topic. 

## Recommendation and Analysis (Business Objective)
Given the LDA results, topic 4 and topic 5 seem to have some overlapping themes about relationships and social connections. While there are some differences in the specific keywords, the overall theme of both topics seems to be centered around relationships and social interactions. It's possible that these topics could be merged into a single, more comprehensive topic that encompasses both relationship-related and social connection-related discussions.

The following proposed topics could be considered to meet the business objective of gaining insights into the specific challenges users face and determine what users hope to achieve through the online community for the purpose of providing online community support and resources to users : 

1. Emotional Support
- Focus : Users to discuss about thier emotional challenges, online community to offer peer advice addressing emotional challenges, and providing resources for mental health support.
- Potential Content : Articles on coping mechanisms, stress management techniques, mental health resources, and community support groups.

2. Relationships and Social Connections
- Focus : Users to share about relationship related challenges and online community to offer peer advice on building and maintaining relationships, overcoming social anxiety, and fostering a sense of belonging.
- Potential Content: Resources on communication skills, dating tips, friendship building, and online community engagement.

3. Self-Esteem and Confidence Building
- Focus : Users to discuss about issues relating to low self confidence and low esteem. Users in the community to discuss about strategies for improving self-esteem, overcoming negative self-perception, and building confidence.
-  Potential Content: Resources on positive affirmations, body positivity, goal setting, and personal development.

4. Navigating Societal Pressures
- Focus: Users to discuss about topics relating to societal expectations, body image issues, and the challenges of fitting in.
- Potential Content: Recources and articles on challenging societal norms, body positivity, and self-acceptance.

5. Personal Growth and Development
- Focus : Users to share resources for personal growth and life skills.
- Potential Content: Articles on personal development strategies, and life skills workshops.

## Buisness Goal Analysis 

<img width="266" alt="image" src="https://github.com/user-attachments/assets/7894300d-67b3-407b-869f-9a1e531912c8">


After launching the online community, we encouraged members to share their daily experiences on the platform. To measure the overall sentiment of the online community and determine if it meets the target of at least a 20% positive sentiment rate, we'll be gathering data from the community members' posts, and analyse the sentiment expressed in the posts. 

![image](https://github.com/user-attachments/assets/d3181f4b-84d6-4d03-907d-e02b91fa3234)


Blue shades represents negative sentiment, grey shades represents neutral sentiment while red shade represent positive sentiment.

The sentiment analysis in this case is performed using the TextBlob library. Based on the color distribution, it appears that negative sentiment is more prevalent in the dataset as there are more blue-shaded bars. Despite the dominance of negative sentiment, there is a range of sentiment scores within each color category. This suggests that while negative sentiment is prevalent, there are also instances of neutral sentiment.

![image](https://github.com/user-attachments/assets/d204a87a-2ad2-48ca-8805-548becf74a6a)

The majority of posts exhibit neutral sentiment, as indicated by the significantly taller grey bar.

Based on the data, the business goal of achieving at least a 20% positive sentiment rate has been met. The red bar representing positive sentiment is above the 20% mark, indicating that a sufficient number of posts express positive emotions.

## AI Ethics
The primary AI ethics concern in this project revolves around issues with privacy where the potential identification of individual users despite the anonymous nature of Reddit may occur. While usernames are publicly visible, other personal information might be inadvertently revealed through: 
-	Post content : personal information, such as location, occupation, or relationships may be revealed within posts. 
-	Cross-platform correlations: Linking Reddit activity to other online profiles through shared information or patterns could identify individuals.
  
To mitigate these risks, I have only collected essential data related to my business objective, which are post and comments, and did not collect usernames which could potentially identify individuals. 

Using keywords like “better” or “improve may also run the risk of introducing bias into the data collection process as focusing on these terms might overemphasis on positive outcomes and overlook negative experiences or challenges faced by the community. However, fortunately that was not the case as the scrapped text data was observed to have a predominantly negative sentiment which is aligned with the overall character of the forever alone subreddit. 

Reddit Application Programming Interface (API) access policies has a strict data usage restriction. These restrictions impact data accessibility and requires researchers or developers to pay for access which not everyone has the financial resource to do so.  This raises concerns about fairness and inclusivity in AI as the restrictions potentially limiting innovation and the diversity of voices in AI research. 

Additionally, Reddit's dataset has been a valuable resource for training AI models, particularly in natural language processing (NLP). The new restrictions could hinder research, particularly in areas like sentiment analysis and language generation. This may slow down advancements in AI and limit the diversity of datasets used in training, potentially leading to models that are less robust or biased.


## Source Codes and Datasets
[Project Source Code and Dataset]([(https://github.com/KdrOHS/ITD214_Project)])
https://github.com/KdrOHS/ITD214_Project


