# stock-predictor
Stock Prediction as a RESTful API using FastAPI to AWS EC2

curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://54.243.8.157:8000/predict
