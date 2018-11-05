# pyFlaskDeploymentGuide

This guide assumes you have a working Python [Flask](http://flask.pocoo.org/) app and have [Heroku-CLI](https://devcenter.heroku.com/articles/heroku-cli) installed on your machine.

1. Install the [gunicorn](https://gunicorn.org/) server: `pip install gunicorn`

2. Install all other dependencies:
  ```
  pip install flask
  pip install flask-sqlalchemy
  pip install pandas
  ...
  ```

3. Run the command:
  ```
  pip freeze > requirements.txt
  ```
  This command will create a _requirements.txt_ file in the current directory that includes all our dependencies (Python packages we use). Heroku will use this file to install all the required dependencies for our app.

4. Create a `Procfile` file (command: `touch Procfile`).

5. Open (edit) `Procfile` and add the following line to it:
 ```
 web: gunicorn <app-folder-name>.app:app
 ```
  _(replacing `<app-folder-name>` with the name of the folder that contains your `__init__.py` file)_

 This file will be used by Heroku to start the gunicorn server and run our app.
 
6. Using the command-line login to heroku: `heroku login` and enter your credentials.

7. Create an Heroku app with the command: `heroku create`

8. Add, Commit and Push your app to Heroku:
```
git add .
git commit -m 'heroku deployment'
git push heroku master
```
