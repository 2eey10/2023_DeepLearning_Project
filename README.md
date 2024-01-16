# 2023 Deep Learning Project

## Binary Classification of MBTI Personality Types Based on Korean Text Data

### Abstract

This project focuses on the binary classification of personality types according to the Myers-Briggs Type Indicator (MBTI) using a substantial corpus of natural language data extracted from media sources. To align with the research objectives, the dataset is constructed by extracting natural language data from MBTI café posts on the Naver portal site. The subsequent preprocessing and refinement stages are followed by an embedding process applied to the cleaned natural language data. The classification performance is then optimized through modeling using LSTM (Long Short-Term Memory) and various machine learning models.

### Project Overview

- **Data Collection:**
  - Utilized natural language data from MBTI café posts on Naver portal site.
  - The research aimed to crawl posts from a variety of boards within Naver's MBTI psychology café, with a focus on identifying the most indicative posts for extroverted and introverted personalities. Among the café's boards, one stood out where authors' personality types were intuitively revealed in their posts, showcasing a diverse range of emotions and personality types. These posts provided a more straightforward understanding of extroverted and introverted traits compared to other board types. It illustrates that each MBTI type had dedicated boards, where authors, identified by their personality type-inclusive nicknames, wrote posts reflecting emotions and themes consistent with their personality types.

- **Data Labelling:**
  - The crawling process involved dividing the data into 'Post' main text and 'Comments' comment data. The crawled data was organized based on authors labeled by MBTI type, including both post data with titles and content and comment data. Utilizing the Selenium package, a dynamic web crawling approach was employed.

- **Data Preprocessing:**
  - The data preprocessing was conducted on labeled post data and comments data. During this process, unnecessary elements for future tokenization, such as special characters, URLs, emoticons, line break characters, and stopwords, were removed from the labeled text data. 
 
- **Data Tokenization:**
  - The preprocessed data underwent tokenization, and for this step, the 'KoNLPy' package was utilized, known for its ease in processing Korean text data. Among several morphological analyzers within KoNLPy, three analyzers, namely 'Kkma,' 'Okt,' and 'Hannanum,' were considered as candidates. When comparing the processing time of each analyzer on the preprocessed data, the 'Okt' morphological analyzer, specifically the 'morphs' function, demonstrated the most efficient processing time. It illustrates the processing time comparison for 1,000 samples using different morphological analyzers. Through this comparison, it was confirmed that, compared to other scenarios, the 'Okt' morphological analyzer's 'morphs' function yielded properly extracted tokens with superior processing time efficiency. After completing the preprocessing, applying the 'morphs' function with the 'Okt' morphological analyzer to the dataset revealed a transformation into a morpheme-separated form.

  
- **Embedding Process:**
  - Applied embedding techniques to represent textual information in a numerical format.
  - The tokenized dataset underwent an embedding process using the word2vec method. This process transformed the dataset into a tensor-shaped embedding vector format. Subsequently, the transformed vector dataset was labeled with '0' for extroversion and '1' for introversion.

- **Modeling:**
  - Models including the 'LSTM Model,' 'Catboost Model,' and 'Logistic Regression Model' were employed for binary classification based on the labeled vector dataset. The performance of each model was compared..
  - For each model, accuracy was used as an evaluation metric, calculated by dividing the correctly labeled values by the total length of the validation dataset. Similarly, the loss value, representing the average loss, was normalized by the length of the validation dataset.


### Repository Structure

- **/data:** Contains the dataset used for training and evaluation.
- **/code:** Scripts and notebooks for data preprocessing, Embedding-related code and documentation, Implemented LSTM and other machine learning models.
- **/results:** The results of modeling based on each tokenization tool


