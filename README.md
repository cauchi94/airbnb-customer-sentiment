# airbnb_customer_sentiment

## Description
Analysis of text data by extracting the main topics from airbnb dataset using **Latent Dirichlet Allocation (LDA)** and then **Linear Regression** to interpret the topics.

## Business Need

Due to the subjective nature of tourist satisfaction in the hospitality industry, even the most influential hosts may struggle to identify the predecessors of guest contentment and dissatisfaction. Because AirBnB's business model is currently decentralized, determining which features are crucial to the customer experience is significantly more difficult. Given that, despite the wealth of data provided by the website Inside Airbnb, there has been little research into the importance of Airbnb hosts, and they would benefit immensely from customer comments to better understand the lodging sector.  
  
In contrast to hotels and hostels, where consumer brand awareness is critical, AirBnB users are willing to pay a premium for a listing based mostly on user evaluations, which are often the most accurate source of information. Therefore, we want to create some guidelines for hosts to improve their customers' experience. To accomplish this, we intend to use the information contained in the listings' evaluations to determine if there is a link between the occurrence of certain topics in listing reviews and an increase in its price or star reviews.  
  
The objective is to understand what listing characteristics boost customers’ experience and pleasure, inspecting general guest feedback, AirBnB listing location qualities, what tangible and intangible features of the listings consumers highlight, the level of service provided by the host, and what customers want or anticipate, as well as the overall management of the listing. Once those topics are identified it will be vital to understand the effect they have on the listing’s price/star rating.

## AI Techniques
  
**1. Latent Dirichlet Allocation (LDA)**  
  
Natural Language Processing for text mining will be employed as the AI approach, with each listing having a document including a matrix of phrases used by consumers while writing their evaluations. Only English words and non-stop words will be examined, and the subjects intrinsic to the collection of descriptive text, in our instance, reviews, will be categorized according to the learned topics to be used later for machine learning models, using Latent Dirichlet Allocation (LDA).  
  
_Advantages_: We utilize LDA because it assigns a probability distribution over topics to each listing, where topics are probability distributions over words. It is a more human-interpretable approach to topic modeling and is an efficient way to analyze enormous quantities of text. Since interpretability is important, the reason why we chose LDA is that compared to other topic modeling algorithms, it offers word distributions. This helps in identifying if a sensible number of topics have been chosen and provides insightful labels to them.  
  
_Disadvantages_: Natural Language Processing can be hard and there is no correct answer as text data presents unique challenges stemming from the qualitative and unstructured nature of the data. The selection of the number of topics to the model will bring about completely different results. Also, with NLP, importance must be put on the distinction of topics to form different segments.

**2. Linear Regression**  
  
Description of the data to be utilized.  
  
All the data cited are referred to the listings in London.  

1) Detailed Review Data for listings includes listing id, the review that the listing refers to, the date of the review, and the text in the review. The analysis may not completely cover the whole timespan present in the data frame but be instead limited to the last disposable year, as customer preferences often are subject to big changes over time and outdated data may lead to wrong insights. The data will then be used to train the LDA.  
  
2) Listings’ Data, including but not limited to price, location, number of beds, bathrooms, and score ratings, to be used to train regression models and understand if the presence of specific topics in a listing’s reviews has an effect on the price/rating score of that listing itself.

## Motivation

By using the topic modeling technique, we aim to uncover hidden structures in user reviews and derive useful insights for hosts to improve their listing’s customer experience.

## Libraries
  
The required libraries to execute all the scripts successfully are the following:  
- _pandas_: data analysis and manipulation tool  
- _numpy_: library for working with arrays
- _os_: to interact with the underlying operating system
- _nltk_: various text processing libraries with a lot of test datasets
- _re_: special text string used for describing a search pattern
- _spacy_: for NLP such as tokenization, named entity recognition with pre-trained models for several languages
- _wordcloud_: a visual representation of text data
- _pprint_: prints Python data structures in a form which can be used as input to the interpreter
- _pyLDAvis_: for interactive topic model visualization
- _gensim_: for representing documents as semantic vectors
- _pickle_: serializing and deserializing a Python object structure
- _scipy.stats_: probability distributions, summary and frequency statistics, correlation functions and statistical tests
- _sklearn.linear_model.LinearRegression_: linear model with coefficients
- _sklearn.compose.ColumnTransformer_: applies transformers to columns of an array or pandas DataFrame
- _sklearn.impute.SimpleImputer_: univariate imputer for completing missing values with simple strategies
- _sklearn.pipeline.Pipeline_: to assemble several steps that can be cross-validated together while setting different parameters
- _sklearn.metrics.classification_report_: to build a text report showing the main classification metrics

## Data

Data for _**reviews.csv**_ and _**listings.csv**_ were both downloaded using: **http://insideairbnb.com/**.
