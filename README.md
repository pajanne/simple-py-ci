
# Create a very simple application using Python to demonstrate continious integration using GitHub


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
