# Social Chatter vs Stock Moves

A personal, non-commercial learning project. It measures how often public
companies are mentioned in online discussion headlines each day and tests,
statistically, whether those mention counts relate to daily stock price
movements.

## Status
In development. Currently prototyping with Hacker News headlines. Reddit
data collection is planned and will begin only if access is approved.

## Planned pipeline
1. **Collect** public post titles and basic metadata (timestamp, score,
   comment count). Read-only.
2. **Classify** which public company, if any, each title is about, using
   a third-party LLM API for classification only (not model training).
3. **Prices** pulled from yfinance and converted to daily returns.
4. **Analyse** in R: do daily mention counts relate to next-day returns?
5. **Display** results in a simple dashboard.

## Reddit data use
- Read-only: the project never posts, votes, comments or messages.
- Collects only title, timestamp, score and comment count from four
  subreddits: r/wallstreetbets, r/stocks, r/StockMarket, r/investing.
- About 100 requests per day, with a descriptive user agent and rate
  limits respected.
- Does not identify, profile or track individual users.
- Reddit content is not used to train any model, and nothing is sold,
  licensed or monetised. There are no ads.

## Tech
Python (requests, pandas, yfinance), R, an LLM API for classification.

## Limitations
Small sample sizes, noisy company-name matching, and mentions that may
follow price moves rather than cause them. Results will be reported
honestly, including null results.
