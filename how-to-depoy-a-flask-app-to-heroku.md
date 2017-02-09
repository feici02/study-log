## How to depoy a Flask app to Heroku?

```hello.py``` is a very simple Flask application. In this tutorial, we'll:
1. run it locally first, and then
2. depoly it to Heroku

Without further ado, let's get our hands dirty.

hello.py
```
import os
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return '<h1>Hello World!</h1>'


if __name__ == '__main__':
#    app.run(debug=True)
    port = int(os.environ.get("PORT", 5000))
    app.run(host='0.0.0.0', port=port)
```

### 1. Run it locally
Please follow steps below:
```
mkdir hello-heroku
cd hello-heroku

# create and activate a virtual env
python3 -m venv venv
. venv/bin/activate
# the prompt will change here

# check the path of Python
which python

pip install flask
pip install gunicorn

gunicorn hello:app
# output on the terminal:
# * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

Now, you can access above URL in the browser.
"Hello Heroku!" will be displayed if everything goes all right.

### 2. Deploy it to Heroku from GitHub
1. Create a repo named "hello-heroku" on [GitHub](https://github.com).
1. Create a [Heroku account](https://id.heroku.com/login).
1. Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).
1. Create an app on Heroku.
```
heroku login
heroku create hello-heroku-feici02
```
1. Configure the integratoin with GitHub on the "depoy" tab of this app.
1. Run the following commands to output a list of all the installed python packages
```
pip freeze >! requirements.txt
```
1. Run the following command to create the "Procfile" which is required by Heroku to deploy the app.
```
echo "web: gunicorn hello:app" > Procfile
```
1. Run the following command to push this app to GitHub.
```
git init
echo "venv\n*.pyc" > .gitignore
git add -A
git commit -m "initial commit"
git remote add origin https://github.com/feici02/hello-heroku.git
git push origin master
```
1. Check the logs to see if everything is OK.
```
heroku logs --app hello-heroku-feici02
```
1. If there are no errors, you can access your app at: hello-heroku-feici02.herokuapp.com

### 3. Deploy it to Heroku directly

If you don't want to use GitHub, you can deploy the app created in Part 1 directly to Heroku. Here are the steps:
```
cd hello-heroku
git init
heroku apps:create hello-heroku-feici02-2
git remote -v
# a remote named heroku will be added to your repo automatically

git push heroku master
# Your app is up and running at: hello-heroku-feici02-2.herokuapp.com.
```

### Reference
1. [Getting Started on Heroku with Python](https://devcenter.heroku.com/articles/getting-started-with-python)
2. [Starting a simple Flask app with Heroku](http://virantha.com/2013/11/14/starting-a-simple-flask-app-with-heroku/)
