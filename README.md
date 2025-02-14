# flask_dynamic_example
Project that uses Flask with dynamic response


# Introduction
This application is a basic API application that uses Flask to create an API that returns a dynamic JSON object. 
An API is a contract between a provider and a user. It is common to create RESTful APIs that can be called by the front end or other clients. In a REST based API, the resource information is sent as part of the request URL. 

# Prerequisites
## Setup Python Project using UV

1. Install UV, a Python project manager
2. Install Python version and create project

```bash
uv python install <VERSION> --path <PATH TO INSTALL>
uv init <NAME OF PROJECT>
```

3. Create Environment
```bash
uv venv --python 3.13
```

4. Activate Environment
```bash
.venv\Scripts\activate
```

5. Add packages
```bash
uv add <PACKAGE NAME>	
```

6. Run Python script:
```bash
uv run <PYTHON SCRIPT NAME>
```

To check that the package added have the correct version and dependencies:

```bash
uv sync
```

Remove package:
```bash
uv remove <PACKAGE NAME>
```


## Install dependencies from pyproject.toml

```bash
uv pip install -r pyproject.toml --all-extras
```

# Running Flask Application
After installing the dependencies, the Flask application can be run. The Flask application can be executed using the following command:


```bash

flask --app app --debug run
```
, where:
- --app: Identifies the Python file to run (which is called in this example app.py), and 
- --debug: Run the server in debug mode

This also can be done by exporting the settings manually (In Windows use `set` instead of `export`) :
```bash
export FLASK_APP=app.py
export FLASK_ENV=development
```
- Run Flask
```bash
flask run
```

## Curl Commands
The following curl commands can be used to test the Flask application:
```bash
curl -X GET -i localhost:5000
curl -X GET -i -w '\n' localhost:5000/no_content
curl -X GET -i -w '\n' localhost:5000/exp
curl -X GET -i -w '\n' localhost:5000/data
curl -X GET -i -w '\n' localhost:5000/count

curl -X GET -i localhost:5000/person/66c09925-589a-43b6-9a5d-d1601cf53287 
curl -X DELETE -i localhost:5000/person/66c09925-589a-43b6-9a5d-d1601cf53287 
```

```bash
curl -X POST -i -w '\n' \
  --url http://localhost:5000/person \
  --header 'Content-Type: application/json' \
  --data '{
        "id": "4e1e61b4-8a27-11ed-a1eb-0242ac120002",
        "first_name": "John",
        "last_name": "Horne",
        "graduation_year": 2001,
        "address": "1 hill drive",
        "city": "Atlanta",
        "zip": "30339",
        "country": "United States",
        "avatar": "http://dummyimage.com/139x100.png/cc0000/ffffff"
```
        
In Windows, single-quoting is not available. Use double quotes and escape the double quotes:
```bash

curl -X POST -i -w '\n' \
--url http://localhost:5000/person  \
--header "Content-Type: application/json"  \
--data "{\"id\": \"4e1e61b4-8a27-11ed-a1eb-0242ac120002\",\"first_name\": \"John\",\"last_name\": \"Horne\", \"graduation_year\": 2001, \"address\": \"1 hill drive\", \"city\": \"Atlanta\", \"zip\": \"30339\", \"country\": \"United States\", \"avatar\": \"http://dummyimage.com/139x100.png/cc0000/ffffff\"}"
```