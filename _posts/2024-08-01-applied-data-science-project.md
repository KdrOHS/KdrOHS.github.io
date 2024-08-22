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

1.High Frequency of Terms related to Relationship and Social Connection: Words like "friend," "someone," "never," "woman," and "relationship." dominate the graph. This indicates a strong desire for relationships, companionship, and social connection.

2.Emphasis on Emotional Struggles: Terms like "alone," "mean," "live," and "give." suggest that users are grappling with feelings of loneliness, rejection, and depression.

3.Search for Solutions:  Users are actively seeking guidance and support to navigate their challenges. This is indicated by terms like "help," "talk," and "always."

4. Self-Esteem and Confidence : While less prominent than the previous themes, there is some evidence of concerns about self-esteem and confidence. This is suggested by terms like "attract" and "girl."


### Modelling
To uncover the underlying latent topics within the dataset, Latent Dirichlet Allocation (LDA) will be employed to identify the primary themes or topics discussed by users. To find the most suitable number of topics, coherence scores and perplexity scores are calculated for different numbers of topics.

![image](https://github.com/user-attachments/assets/4b44c0f0-5ca5-48a4-94ae-d876d75b1822)
The coherence graph reaches a peak at around 10 topics. This indicates that a model with 10 topics provides the highest coherence score, suggesting it effectively captures the latent themes in the data. Beyond 10 topics, the coherence score starts to decrease. This suggests that adding more topics might lead to overfitting or less meaningful topic interpretations.

![image](https://github.com/user-attachments/assets/6d1d5b6d-84ab-4465-b39b-0fa6c6f59b77)
The perpelxity graph reaches a plateau around 8-10 topics. This suggests that adding more topics beyond this point doesn't significantly improve the model's fit.After the plateau, the perplexity score starts to increase slightly. This might indicate that adding too many topics could lead to overfitting or less meaningful topic interpretations.

Based on the coherence and perplexity graphs, choosing 6 topics for the LDA model is a reasonable decision, especially given the relatively small dataset of 190 documents. While the coherence score continues to increase slightly beyond 6 topics, the improvement may not be substantial enough to warrant the additional complexity. The perplexity score plateaus around 8-10 topics, but there's a relatively small difference between the perplexity scores for 6 and 10 topics. With fewer topics, the results may be easier to interpret and understand.


### Evaluation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis
Explain the analysis and recommendations

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

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


