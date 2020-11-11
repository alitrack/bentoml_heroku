# bentoml_heroku
A BentoML Heroku example

## Prerequisites

```sh
pipenv install bentoml scikit-learn pandas
```

## Build

```
git clone https://github.com/bentoml/BentoML
pipenv install -r ./BentoML/guides/quick-start/requirements.txt
pipenv  run python ./BentoML/guides/quick-start/main.py

cp -rf $(pipenv run bentoml get IrisClassifier:latest --print-location --quiet)/IrisClassifier IrisClassifier

echo 'web bentoml  serve-gunicorn IrisClassifier   -p $PORT' >Procfile
```

## Deploy

### Heroku Cli

login with `heroku login` first,

then 

```sh
export APP = bentoml_heroku

heroku create $APP

git init
heroku git:remote -a $APP
git add .
git commit -m "BentoML Heroku Cloud"
git push heroku master

```

### GitHub
- fork the rep
- connect GitHub with your Heroku
- deploy it. 


## ref

* [Deploying BentoML to Heroku,the Docker way](https://docs.bentoml.org/en/latest/deployment/heroku.html) 




