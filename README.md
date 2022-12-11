# Reddit-Recommendation-System

## Explanation of the files:

crawler_and_preprocess.ipynb: preprocess data to generate 3 CSVs for training

sg.ipynb: the core of our project: using GNN to build a recommendation system

community_keyword_extractor.ipynb: extract keywords from subreddit descriptions

mbti_classification.ipynb: using DistilBERT to build an MBTI classifier

(In preprocess.ipynb we also used a CSV called [reddit_data.csv](https://www.kaggle.com/datasets/colemaclean/subreddit-interactions). This dataset is rather large (~500MB) so we didn't include the binary in this repo. This CSV is only used in preprocess, not in training! We just have to use our own generated CSVs for training.)

Data: 1K: nodes_subreddit_1000.csv + nodes_user_1000.csv + edges_1000.csv : preprocessed training data for 1K data points.
      50K: edges_50K.csv + nodes_subreddit_50K_top_1000_keywords.csv + nodes_user_50K_mbti.csv : our final training data, it takes about 48 hours to craw these on a school's CCV compute node
      
The MBTI datasets below are too large (~64M and ~350M respectively), so we did not include them in the repo either. But they can be found through links below:
    
- [mbti.csv](https://www.kaggle.com/datasets/datasnaek/mbti-type): a Kaggle MBTI dataset of posts from 8600 users * 50 sentences per user
      
- [MBTI_500.csv](https://www.kaggle.com/datasets/zeyadkhalid/mbti-personality-types-500-dataset): a Kaggle MBTI dataset of ~1.7M records of posts collected from Reddit. 

## Our overall structure:

* using PRAW to craw some more features for redditors and subreddits
* using KeyBERT to extract keywords as a feature for subreddits
* training a DistilBERT-based MBTI classifier, based on redditor's past posts to add a feature for redditors
* using GNN for recommendation system (StellarGraph + Heterogeneous GraphSAGE (HinSAGE) + Link Prediction)
