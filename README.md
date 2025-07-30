# sentimentAnalysis
Analysis of Social media sentiments for a company's prducts

How to Run:
1. open sentimentAnalysis jupyter notebook
2. It has a link to google colab in top (in case of running the code)
3. For viewing, the notebook can be viewed directly in github. It has all the explanations and analysis done in the result section
4. On opening the colab notebook choose the necessary resources used for compute (CPU or GPU). I had used L4 GPU
5. RunAll - it will prompt for Github token to clone repo into the cluster.
6. Once done everything runs cell by cell
7. Prerun notebook available with the name "SentimentAnalysis_withOutputs.ipynb"

Data Schema:
Engagements Table
timestamp object
media_id int
media_caption text
comment_text text

Data:
1. Media_id is the unique id for media_caption
2. comment_text can be user comments/ blank/ mentions eg. @<mentions>
3. timestamp is when users comment for each media

Overall Idea:
1. The idea here is to splice to data to understand the user sentiments by different categories
2. We need to capture the user sentiments for each comments and splice them by media
3. moreover each media_cpation can be clustered where some captions may belong to similar semantic meaning. Hence we can analyse the sentiments by clusters as well

Approach:
1. Data Clensing
2. Using Kmeans clustering find the ideal number of clusters to segregate the media into
3. Run Sentiment analysis using a BERT model
4. Analyse the results

AI tools used:
1. Infra - Google Colab: L4 GPU
2. GitHub
3. Pretrained Language model Framework library - Huggingface Transformer
4. Clustering model - 'all-mpnet-base-v2'
5. Sentiment Analysis RoBERTa model- "cardiffnlp/twitter-roberta-base-sentiment"
6. Summarizer model - "facebook/bart-large-cnn"

Future work:
1. When more features are available, we can actually analyze the data by product category, product id etc.
2. Obtain comments and views from different social media platforms
3. use a supervised learning set to train the sentiments and fine tune the language models for it to predict specific sentiments
4. Give a crisp summary of the user comments by product, media, sentiment etc.,
5. detect anomalies and if comments available by user unique identifier, can filter or analyze repeated comments
6. Multimodel handling is not done here in this project. We can extend the analysis to text, pictures, GIF's ,videos etc.
7. Can extend the analysis across languages
