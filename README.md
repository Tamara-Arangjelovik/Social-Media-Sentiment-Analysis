Sentiment-Analysis

These scripts collectively provide a robust framework for collecting, processing, and analyzing social media data from Twitter and YouTube. They enable researchers to:
Gather Data: Collect tweets and YouTube comments related to specified topics.
Clean and Prepare Data: Ensure the text is in a usable format for analysis.
Analyze Sentiments: Classify emotions and sentiments in the data.
Visualize Results: Create bar plots and word clouds to uncover patterns and trends.
They are particularly useful for understanding how people engage with and react to topics like the Ukraine-Russia war and other trending topics across different platforms.


1. Python Script for Collecting Tweets
This script is designed to collect tweets about Ukraine using Twitter’s API to understand public opinion during a specific time frame, focusing on English-language tweets and excluding retweets. It saves the data in a structured format for further analysis.
Libraries: Utilizes datetime, json, and Twarc2 to interact with Twitter’s API and handle data efficiently.
Authentication: Logs into Twitter using a Bearer Token, which you must provide. This token acts as a key to access Twitter’s API.
Time Range: Targets tweets posted between February 24, 2022, and March 2, 2022, capturing a specific period of interest.
Search Query: Searches for tweets containing the keyword "Ukraine" in English, filtering out retweets to ensure originality.
Data Storage: Saves the collected tweets in a .jsonl file (ukraindatadump.jsonl) and converts the .jsonl file into a .csv file (ukraindatadump.csv), making it easier to analyze the data in tools like Excel.


2. R Script for Text Mining and Visualization
This script processes and analyzes tweet data using text mining techniques and creates visualizations like bar plots and word clouds to uncover patterns and trends in the text.
Loading Data: Allows you to select a CSV file containing tweets and loads it into a data frame called UKTwit. It also displays the structure of the data, including column names and data types.
Building the Corpus: Converts the tweet text into a "corpus," a collection of text documents, and cleans the text by converting it to ASCII format.
Text Cleaning: Prepares the text for analysis by: Converting all text to lowercase, removing punctuation, numbers, and common stopwords (e.g., "the," "and") and eliminating extra whitespace.
Term-Document Matrix (TDM): Creates a matrix that shows how often each word appears in the tweets, providing a quantitative basis for analysis.
Visualizations:
Bar Plot: Displays the most frequent words (appearing at least 25 times) in a colorful bar plot.
Word Cloud: Generates a word cloud where the size of each word corresponds to its frequency, offering a visually appealing way to identify key themes.
Advanced Word Cloud: Uses the wordcloud2 package to create an interactive word cloud in a star shape with a black background, adding a creative touch to the analysis.


3. R Script for Collecting YouTube Comments
This script gathers and organizes comments from YouTube videoa using the vosonSML package and saves the data to a CSV file for further analysis.
Loading the Package: Uses the vosonSML package to collect and analyze social media data. If the package isn’t installed, it prompts you to install it.
YouTube API Key: Authenticates with YouTube’s API using a provided API key (you need to replace the placeholder with your own key).
Data Collection: Specifies a YouTube video by its ID and collects comments and replies, storing the data in a variable called ytdata.
Saving Data: Saves the collected comments into a CSV file (ukraindatadump-youtube.csv) for easy access and analysis.
Data Inspection: Displays the structure of the collected data and provides a preview of the first few rows, allowing you to quickly understand the dataset.


5. R Script for Sentiment Analysis on Tweets
This script analyzes the emotions and sentiments in tweets about the Ukraine-Russia war using the syuzhet package and visualizes the results with a bar plot.
Loading Libraries: Uses the syuzhet package for sentiment analysis, along with other libraries like ggplot2 and dplyr for additional functionality.
Reading Data: Lets you select a CSV file containing tweets and loads it into a data frame called mf. It also cleans the tweet text to ensure compatibility with the sentiment analysis functions.
Sentiment Analysis: Uses the get_nrc_sentiment function to classify each tweet into 10 sentiment categories (e.g., joy, anger, fear, trust) based on the NRC Emotion Lexicon.
Visualization: Creates a colorful bar plot to display the total count of each sentiment category across all tweets, providing a clear overview of the emotional tone of the dataset.


6. R Script for Sentiment Analysis on YouTube Comments
This script performs sentiment analysis on YouTube comments about Ukraine, similar to the tweet analysis script, but tailored for YouTube data.
Loading Libraries: Uses the syuzhet package for sentiment analysis and other supporting libraries.
Reading Data: Lets you select a CSV file containing YouTube comments and loads it into a data frame called mf. It also cleans the comment text for analysis.
Sentiment Analysis: Applies the get_nrc_sentiment function to classify each comment into 10 sentiment categories, storing the results in a data frame.
Visualization: Creates a bar plot to visualize the sentiment scores, offering insights into the emotional tone of the comments.
