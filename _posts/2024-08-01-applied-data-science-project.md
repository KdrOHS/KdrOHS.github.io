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
   
To measure the project's success in enhancing user emotional well-being, we will aim to increase positive sentiment expressed in user posts by 20%.
As for my part of the project, I will be focusing on business objective 2 to uncover the primary topics discussed within the r/ForeverAlone community.


## Work Accomplished
### Data Collection 

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
-	Due to the specific keywords and subreddit nature, only 189 posts were available for scraping out of the intended 1000.
-	Iterate through the scraped posts, extracting relevant information (title, post, comments, URL).
-	Store the extracted data in a list.
5. Export to CSV File:
- Define the CSV file name (FA_improve.csv).
- Write the scraped data (post titles, posts, comments, URLs) to the CSV file.

The terms "improve" or "better" might seem limited in scope, but they can indirectly provide insights into the challenges faced by the r/ForeverAlone community and their aspirations.

Users often express their desire for improvement in areas where they perceive shortcomings. For example, posts containing "improve social skills" can indicate challenges in social interaction.

Users seeking to "better" their situation will also reveal their desired outcomes. 


### Data Preparation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

### Modelling
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

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


