# pyFlaskDeploymentGuide

1. Install gunicorn: `pip install gunicorn`

2. Install all other dependencies:
  ```
  pip install flask
  pip install flask-sqlalchemy
  pip install pandas
  ...
  ```

2. Run the command:
  ```
  pip freeze > requirements.txt
  ```
  This command will create a _requirements.txt_ file in the current directory that includes all our dependencies (Python packages we use). Heroku will use this file to install all the required dependencies for our app.

3. Create a `Procfile` file (`touch Procfile`).

4. Open (edit) `Procfile` and add the following line to it:
 ```
 web: gunicorn <app-folder-name>.app:app
 ```
  _(replacing `<app-folder-name>` with the name of the folder that contains your `__init__.py` file)_

 This file will be used by Heroku to start the gunicorn server and run our app.
