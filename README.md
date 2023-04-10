
# Building and Deploying a Stock Prediction Model
I will be deploying a stock prediction model as a RESTful API using [FastAPI](https://fastapi.tiangolo.com/) to AWS EC2, and make it available (i.e., public) to end users. 

## Deliverables 

We will use [Prophet](https://facebook.github.io/prophet/) to predict stock market prices. 
We defined three functions here:

1) `train` downloads historical stock data with [`yfinance`](https://github.com/ranaroussi/yfinance), creates a new Prophet model, fits the model to the stock data, and then serializes and saves the model as a [`Joblib file`](https://joblib.readthedocs.io/en/latest/generated/joblib.dump.html).

2) `predict` loads and deserializes the saved model, generates a new forecast, creates images of the forecast plot and forecast components, and returns the days included in the forecast as a list of dicts.

3) `convert` takes the list of dicts from predict and outputs a dict of dates and forecasted values; e.g., {"07/02/2020": 200}).

4) The last block of code allows you to execute the model from the command line, with two arguments, a valid stock ticker and the number of days to predict.

# Build Container Image for FastAPI Applications
Build a container image for your FastAPI application.

curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://54.243.8.157:8000/predict


# Acknowledgement & Reference

- Adapted from [Deploying and Hosting a Machine Learning Model with FastAPI and Heroku](https://testdriven.io/blog/fastapi-machine-learning/)
- To learn about API in general, [Postman Learning Center](https://learning.postman.com/docs/getting-started/introduction/) is a good starting point.
- [Machine Learning Operations (MLOps): Overview, Definition, and Architecture (July 2022)](https://arxiv.org/ftp/arxiv/papers/2205/2205.02302.pdf)
