# Account Verification with Authy 

[![Build Status](https://travis-ci.org/TwilioDevEd/account-verification-flask.svg?branch=master)](https://travis-ci.org/TwilioDevEd/account-verification-flask)

This example application demonstrates how to implement Account Verification
in a Python Flask application using [Authy](https://www.authy.com/developers/).

## Quickstart

### Create an Authy app

Create a free [Authy account](https://www.authy.com/developers/) if you haven't
already and then connect it to your Twilio account.

### Local development

This project is built using the [Flask](http://flask.pocoo.org/) web framework.
For now, it only runs on Python 2.7 (not 3.4+).

To run the app locally, first clone this repository and `cd` into its directory. Then:

1. Create a new virtual environment:
    - If using vanilla [virtualenv](https://virtualenv.pypa.io/en/latest/):

        ```
        virtualenv venv
        source venv/bin/activate
        ```

    - If using [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/):

        ```
        mkvirtualenv authy2fa-flask
        ```

1. Install the requirements:

    ```
    pip install -r requirements.txt
    ```

1. Create a `local.py` file inside the  `account_verification_flask/config` directory and add it the following 
content. Be sure to replace the place holders and connection string with real information

    ```
    AUTHY_KEY = 'your_authy_key'

    TWILIO_ACCOUNT_SID = '[your_twilio_account_sid]'
    TWILIO_AUTH_TOKEN = '[your_twilio_auth_token]'
    TWILIO_NUMBER = '[your_twilio_phone_number]'

    SQLALCHEMY_DATABASE_URI = 'sqlite:////path/to/your/sqlite_db_file.db'
    ```

1. Run the migrations with:

    ```
    python manage.py db upgrade
    ```

1. Start the development server

    ```
    python runserver.py
    ```

That's it

## Run the tests

You can run the tests locally through [coverage](http://coverage.readthedocs.org/):

1. Optionally create a separate test database and update your `DATABASE_URL` environment variable if you don't want your development data overwritten

1. Run the tests:

    ```
    $ coverage run manage.py test
    ```

You can then view the results with `coverage report` or build an HTML report with `coverage html`.

## Meta

* No warranty expressed or implied. Software is as is. Diggity.
* [MIT License](http://www.opensource.org/licenses/mit-license.html)
* Lovingly crafted by Twilio Developer Education.