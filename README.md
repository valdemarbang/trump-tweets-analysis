# Correlating Trump's Social Media Activity with the Bitcoin Price

This project investigates the impact of Donald Trump's Truth Social activity on Bitcoin market movements, specifically focusing on the period following the 2024 election. By aligning Bitcoin price data with the social media timestamps, this project uses an event study approach to measure price returns across time windows ranging from 30 minutes to 4 hours. The analysis indicates strong divergence in market reactions, while posts containing crypto related terms like "btc" and "cryptocurrency" trigger positive returns, general economic keywords often resulted in negative performance. However, due to the limited number of posts containing the keywords, exact conclusions cannot be drawn. Furthermore, sentiment analysis using VADER found no significant correlation between posts and comments against the Bitcoin price returns. 

## Datasets
### Trump posts
https://huggingface.co/datasets/notmooodoo9/TrumpsTruthSocialPosts

This dataset contains posts and comments scraped from Truth Social, focusing on Donald Trump’s posts (“Truths” and “Retruths”).
Due to the initial collection method, all media and URLs were excluded. Future versions will include complete post data, including images and links. Contains 31.8Million Comments, and over 18000 Posts all By Trump. As well as logged over 1.5Million unique users who commented on his posts. 

### Bitcoin price
https://huggingface.co/datasets/FamilyLinks/btc-price-1m-2017-2025

This dataset provides a granular view of the Bitcoin market by combining 1-minute OHLCV price action (sourced from Binance) with Macro On-Chain indicators (sourced from CryptoQuant).

## Results

### Keyword Analysis vs. Baseline
The analysis compared specific keywords against a baseline average of all data. While the baseline 1-hour return for Bitcoin was approximately 0.0126%, posts containing specific crypto terms saw significantly higher returns.

| Keyword | Count | 1h Return % | 4h Return % | Post Sentiment |
| :--- | :--- | :--- | :--- | :--- |
| **Baseline** | *All* | **0.0126** | **0.0992** | **0.3197** |
| btc | 1 | 2.1660 | 2.7601 | 0.8221 |
| cryptocurrency | 1 | 1.4771 | 0.7112 | 0.9432 |
| crypto | 9 | 0.7717 | 1.4611 | 0.7303 |
| economy | 143 | 0.0391 | 0.1695 | 0.7408 |
| financial | 36 | -0.0676 | 0.2401 | 0.6522 |
| fed | 33 | -0.1152 | 0.0057 | -0.0087 |
| payment | 4 | -0.3105 | -0.8019 | 0.0548 |


### Sentiment Findings
Unlike observations from the 2017-2020 presidency regarding Twitter, this project found no clear correlation between sentiment scores and price returns. For example, keywords like "financial" had positive sentiment scores (0.6522) but negative 1-hour returns (-0.0676).

## Limitations

* **Sample Size:** Some of the keywords like "btc", "bear", or "cryptocurrency" only have a very small sample size (1 post). Which makes the ROI less reliable for those keywords. 
* **Sentiment Tool:** VADER might not be suitable for this project, and it might be better to use a machine learning algorithm instead to analyse the sentiment score. The problem with VADER is that it is rule-based, which mean that it might not handle specific "crypto-slang", such terms as "HODL", "Moon" or "FUD", potentially skewing the sentiment for the comments.
