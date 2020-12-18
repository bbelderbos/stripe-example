# Stripe Checkout Demo

## Get it working locally

Repo to play with [this demo](https://github.com/stripe-samples/checkout-one-time-payments).

The best way to get that running is to use the Striple CLI as per [this instruction](https://github.com/stripe-samples/checkout-one-time-payments#how-to-run-locally) (this will populate `server/.env` which I had to hide in `.gitignore`)

## Deploy it to Heroku

Steps I had to do to get it working on Heroku:

1. Make a Heroku app: `heroku create ...`

2. Define a Python version: `echo python-3.9.1 > runtime.txt`

3. I had to remove the `Gemfile`, otherwise Heroku would think it was a Ruby app.

4. Copy `server/requirements.txt` to `requirements.txt` and `pip install` + add `gunicorn` to it

5. Define what kicks off the Flask app: `echo "web: gunicorn server.server:app" > Procfile`

6. Deploy: `git push heroku master`
