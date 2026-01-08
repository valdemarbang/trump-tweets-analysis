# trump-tweets-analysis
The goal of this repo is to analyse the sentiment of Donald Trumps tweets and also the comments on the tweets. A correlation will then be checked between the posts and the bitcoin price movement.


# Datasets

## Trump posts
https://huggingface.co/datasets/notmooodoo9/TrumpsTruthSocialPosts

This dataset contains posts and comments scraped from Truth Social, focusing on Donald Trump’s posts (“Truths” and “Retruths”).
Due to the initial collection method, all media and URLs were excluded. Future versions will include complete post data, including images and links. Contains 31.8Million Comments, and over 18000 Posts all By Trump. As well as logged over 1.5Million unique users who commented on his posts. 

## Bitcoin price
https://huggingface.co/datasets/FamilyLinks/btc-price-1m-2017-2025

This dataset provides a granular view of the Bitcoin market by combining 1-minute OHLCV price action (sourced from Binance) with Macro On-Chain indicators (sourced from CryptoQuant).