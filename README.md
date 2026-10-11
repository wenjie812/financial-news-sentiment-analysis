# Financial News Sentiment Analysis and Stock Market Research

A Python research project that combines financial news sentiment
with historical stock market data.

## Project Objective

Build a reproducible workflow to investigate whether financial
news sentiment can add predictive value beyond historical prices
and trading volume.

## Current Features

- User-selected stock ticker and company configuration
- Historical price and trading volume dashboards
- News retrieval and manually supplied sources
- Article deduplication and company relevance review
- FinBERT sentiment classification and continuous sentiment scores
- Separate human sentiment review
- Persistent storage by ticker and analysis run
- Incremental processing of new or changed articles
- Timestamp-aware daily news features
- Training-readiness checks

## Tools

Python, pandas, yfinance, Matplotlib, PyTorch,
Hugging Face Transformers, and Jupyter Notebook.

## Methodology

The pretrained ProsusAI/finbert model classifies available titles
and excerpts as positive, neutral, or negative.

Sentiment score = positive-class probability minus
negative-class probability.

Daily features include article count, mean sentiment, and
negative news share. Publication and acquisition timestamps
are used to reduce look-ahead bias.

The daily cutoff is 8:00 p.m. America/New_York.
The outcome is the next observed trading session's
open-to-close return.

## How to Run

1. Open the notebook in Jupyter.
2. Install dependencies using the first installation cell.
3. Run the remaining sections in order.
4. Enter a ticker and company name, or load a saved analysis.
5. Retrieve data, review relevance, and score eligible articles.
6. Generate summaries and daily features.
7. Save the project and reload the same run to accumulate data.

The first FinBERT use requires an internet connection
to download the pretrained model.

## Current Status and Limitations

This project currently implements news analysis and data
preparation. A stock return prediction model has not yet
been trained or evaluated.

News coverage is partial. Model sentiment can be incorrect,
particularly with ambiguous headlines or limited context.
Sentiment scores are not stock movement probabilities.

The 72-hour freshness window is a configurable research
assumption, not an estimated duration of market impact.

## Planned Development

- Accumulate additional timestamped observations
- Compare price-based and news-enhanced models
- Evaluate models using chronological training and test periods
