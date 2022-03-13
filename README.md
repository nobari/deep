# step by step classification for Production

> It is as example for creating a classification model for production

We will walk through:

- building a Deep Neural Network that predicts labels given features (using scikit-learn and Keras)
-- the entire model creation is explained in details in (this notebook)[]
- build a REST API that predicts labels based on the model (using Flask and gunicorn)
- deploy the model to production on Google App Engine

# Quick start

Requirements:

- Python 3.7
- Google Cloud Engine account
- [Google Cloud SDK](https://cloud.google.com/sdk/install)

Clone this repository:

```bash
git clone git@github.com:nobari/X.git
cd X
```

Install libraries:

```bash
pip install -r requirements.txt
```

## Start local server

```bash
flask run
```

## Make predictions

```bash
curl -d '{"neighbourhood_group": "Brooklyn", "latitude": 40.64749, "longitude": -73.97237, "room_type": "Private room", "minimum_nights": 1, "number_of_reviews": 9, "calculated_host_listings_count": 6, "availability_365": 365}' -H "Content-Type: application/json" -X POST http://localhost:5000
```

## Deploy to Google App Engine

```bash
gcloud app deploy
```
