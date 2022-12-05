# Reddit-Recommendation-System

## Explanation of the files:

preprocess.ipynb: preprocess data to generate 3 CSVs for training

nodes_subreddit_1000.csv + nodes_user_1000.csv + edges_1000.csv : preprocessed training data

sg.ipynb: the core of our project: using GNN to build a recommendation system

community_keyword_extractor.ipynb: extract keywords from subreddit descriptions

## Our overall structure:

* using PRAW to craw some more features for redditors and subreddits
* using KeyBERT to extract keywords as a feature for subreddits
* training a MBTI classifier based on redditor's past posts to add a feature for redditors
* using GNN for recommendation system (StellarGraph + Heterogeneous GraphSAGE (HinSAGE) + Link Prediction)
