
# Continuous integration example

## Description
Create a very simple application using Python to demonstrate the usage of continuous integration using [GitHub](https://github.com/) and [Travis](https://travis-ci.org).

## Installation
```
python3 -m venv venv
source venv/bin/activate
```

## Usage
```
source venv/bin/activate
python tests.py
```

### Continious integration using Travis

- Create a `requirements.txt` file with all Python dependencies
```
pip freeze > requirements.txt
```

In this project, we are not using any additional library, that’s why our requirements.txt will be empty but always remember this step.  

- Create a file `.travis.yml`
```
language: python
python:
  - "3.6"
# command to install dependencies
install:
  - pip install -r requirements.txt
# command to run tests
script:
  - python tests.py
```

- Push these new files into your repository and setup Travis
```
git add .; git commit -m 'add ci files'
git push
```

Go to [Travis dashboard](https://travis-ci.org/), connect your Github account then sync your repositories and add the new project.
After every code commit, a build will start automatically and you will be notified by email on its status.
