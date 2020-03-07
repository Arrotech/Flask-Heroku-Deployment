# Heroku Setup

If you haven’t already, create a Heroku account, download and install the Heroku Toolbelt, and then in your terminal run heroku login to log in to Heroku.

Once done, create a `Procfile` in your project’s root directory:

    $ touch Procfile

Add the following line to your newly created file

    web: gunicorn app:app

Make sure to add gunicorn to your requirments.txt file

    $ pip install gunicorn==19.4.5
    $ pip freeze > requirements.txt

We also need to specify a Python version so that Heroku uses the right Python Runtime to run our app with.
Simply create a file called runtime.txt with the following code:

    python-3.6.8


## Create Heroku App

Then create two new Heroku apps.

**One for production:**

    $ heroku create arrotech-pro

**And one for staging:**

    $ heroku create arrotech-stage

Add your new apps to your git remotes. Make sure to name one remote pro (for “production”) and the other stage (for “staging”):

    $ git remote add pro git@heroku.com:arrotech-pro.git
    $ git remote add stage git@heroku.com:arrotech-stage.git

Now we can push both of our apps live to Heroku.

    For staging: git push stage master
    For production: git push pro master

Once both of those have been pushed, open the URLs up in your web browser and if all went well you should see your app live in both environments.