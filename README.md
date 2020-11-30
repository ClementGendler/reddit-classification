### Problem Statement

Is it feasible to use modeling to predict the original subreddit of a post? If so, which model performs best?

### Executive Summary

This project reads 5000 posts overall for the anime and manga subreddits, using two models to predict from which subreddit the posts came based on the title. First, a function is created to retrieve all the data. Then, the data set is manually cleaned to ensure as high accuracy as possible and care when handling the unique range in post characters within these subreddits. The two subreddits are combined into one data set, which is further cleaned by removing null values, replacing [removed] and [deleted] tags with empty stirngs, and a label column is created in preparation for modeling that distinguishes which subreddit a row is from.

Exploratory data analysis and preprocessing are handled via a WordCloud visual to show the word range, indicating prevalent words that can be attributed to one of the two subreddits. In addition, a plot of the top 10 words and their frequencies is displayed. RegExpTokenizer is utilized to manually tokenize title and post columns. Then, tokens are lemmatized to reduce verbs and improve accuracy even further. Stemming was attempted at some point but it was too strong of a tokenizing mechanism for this project. Preprocessing and lemmatizing functions were modified and mapped to the columns, looping back to join the tokenized data into a string form.

Two models were tested: a basic LogisticRegression and a basic MultinomialNB, both with a CountVectorizer to further clean and process the data. To my surprise, the LogisticRegression proved to be more accurate, which I justify later within the project. I follow up by making conclusions and recommendations based on my findings. 

### Conclusions and Recommendations

Logistic Regression is the most accurate model tested, sporting roughly an **89%** accuracy. While not included in this notebook, testing the same type of model multiple times led to differing accuracies, so creating multiple models with slight tweaks could be used to maximize accuracy. CountVectorizer automates a large portion of the manual cleaning I did without reducing accuracy. I'd recommend adding more features to the API and to models to strengthen accuracy as well as potential for modeling.

### Outside Research Sources

https://gist.github.com/MrEliptik/b3f16179aa2f530781ef8ca9a16499af
https://www.datacamp.com/community/tutorials/wordcloud-python
https://www.reddit.com/r/anime
https://www.reddit.com/r/manga