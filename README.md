# ML for portfolio management project

This is a project for a ML for portfolio management class at ENSAE Paris.

The inspiration for this project stems from the paper _"Leadership, Gender, and Discourse in Monetary Policy: Analyzing Speech Dynamics in the FOMC"_ (https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5002334), and treats on the study of monetary policy across the gender divide. 

Central bank speeches are a critical medium for conveying monetary policy intentions and market expectations, as well as communicating economic insights. The content and tone of these speeches can influence public perception and financial markets. However, limited research has been done to explore how these dynamics vary across gender, among central bank speakers. The aim of this project is to help fill this gap by investigating whether male and female central bank leaders differ in their communication styles using NLP techniques, focusing on the topics they address (**topic modeling**) and the tone of their speeches (**sentiment analysis**).
 
Key resources include NLP libraries such as gensim, nltk and scikit-learn, as well as sentiment lexicons like Loughran-McDonald. The dataset of speeches and metadata was created through web scraping the BIS website, requesting the BIS API, and then enriched using the genderize.io API for speaker gender identification.
Other reference that was used : _Information in Central Bank Sentiment: An Analysis of Fed and ECB Communication_ (https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4797935).




## DATASET OVERVIEW
To conduct this analysis, we compiled a novel dataset of speeches delivered by european central bank Governors and senior central bankers, published by the Bank for International Settlements.

The dataset is composed of all central bankers' speeches avilable on the BIS website, coming from european central banks institutions. The speeches date from 2009 up until 2024. The data was requested through the BIS API and the speeches themselves were scrapped from the individual BIS speeches html pages. \
⚠️​ The data collecting function takes a while to run as there are about 20000 speeches on the BIS website that are then filtered and scrapped
The get_central_bank_speeches_urls function requests all speeches individual urls and the load_central_banks_speeches requests all speeches metadata information and then scrapes the speeches content from the html pages if the filter of the institution correponds.
The gender information is added through requesting the genderize.io API. (a mapping dictionary is also provided in case the API request doesn't go through

## Structure and results
The project was specifically required to be able to be run on a single notebook from beginning to end. This is why there is no need for a virtual environment, all the dependencies needed can be found at the very beginning of the notebook.\
To read this project, just run the _projectv1.ipynb_ notebook. Careful that it takes multiple hours to run as we are scraping the speeches from the BIS website and this takes a while. The modeling part may also be quite long.
