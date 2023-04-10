
# Building and Deploying a Stock Prediction Model
I will be deploying a stock prediction model as a RESTful API using FastAPI to AWS EC2, and make it available (i.e., public) to end users. 

We will use Prophet to predict stock market prices. We defined three functions (this model was developed by Andrew Clark):

1) train downloads historical stock data with yfinance, creates a new Prophet model, fits the model to the stock data, and then serializes and saves the model as a Joblib file.

2) predict loads and deserializes the saved model, generates a new forecast, creates images of the forecast plot and forecast components, and returns the days included in the forecast as a list of dicts.

3) convert takes the list of dicts from predict and outputs a dict of dates and forecasted values; e.g., {"07/02/2020": 200}).

4) The last block of code allows you to execute the model from the command line, with two arguments, a valid stock ticker and the number of days to predict.

# Build Container Image for FastAPI Applications
Stock Prediction as a RESTful API using FastAPI to AWS EC2

curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://54.243.8.157:8000/predict
