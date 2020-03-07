# Heroku Setup

If you haven’t already, create a Heroku account, download and install the Heroku Toolbelt, and then in your terminal run heroku login to log in to Heroku.

Once done, create a `Procfile` in your project’s root directory:

    $ touch Procfile

Add the following line to your newly created file

    web: gunicorn app:app

Make sure to add gunicorn to your requirments.txt file

    $ pip install gunicorn==19.4.5
    $ pip freeze > requirements.txt

We also need to specify a Python version so that Heroku uses the right Python Runtime to run our app with. Simply create a file called runtime.txt with the following code:

    python-3.6.8