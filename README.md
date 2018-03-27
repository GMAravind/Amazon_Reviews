# Objective
The motivation of the project is to understand factors influencing helpfulness of a given review. The reivews of the cell and accessories category were considered for the analysis.

# Data Overview
reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B
asin - ID of the product, e.g. 0000013714
reviewerName - name of the reviewer
helpful - helpfulness rating of the review, e.g [2,3]
reviewText - text of the review
overall - rating of the product
summary - summary of the review
unixReviewTime - time of the review (unix time)
reviewTime - time of the review (raw)

# Analysis

## Step 1: Generate helfulness feature
Engineer the helfulness metric from the "helpful" columns. helpfulness ranges from 0-1.
## Step 2: Data Cleaning
Remove special characters and digits from reviews
Tokenization - The process of converting a review from its natural to a list of words
Stop Words Removal - Remove commonly occuring words which does not add much value to find underlying patterns in text eg."the","which","is","that" etc.
Stemming - Reducing different form of words to its basic form which enhances the learning power of the algorithm eg: "cats" and "cat" will be reduced to "cat" 
## Step 3: Data Preparation
Topic Modelling requires data in the form of documents. Here, the combined reviews for each product will act as a document.
## Step 3: Topic Modelling
Apply LDA on the prepared dataset for different combinations of number of topics to identify latent topics in the data.
## Step 4: Segregate sentences from each review into sentences of identified topics
Define functions to scan for keywords belonging to a topic to segregate sentences of a review into sentences of identified topics.
For example -  A review can have 2 sentences corresponding to topic 1 and a sentence corresponding to topic 2.
## Step 5: Sentiment Analysis
Compute the sentiment and subjectivity for the segregated sentences of each review
## Step 6: Regression
With Sentiment and subjectivity of the topics as features for a review and helpfulness as the target variable. Apply regression to construct a model to predict helpfulness of a review

#  Conclusion
Latent Topics - Charge/Battery and Case/Protection.
It is found that reviews are found to be helpful if reviews had a negative sentiment about the product in both the topics.









