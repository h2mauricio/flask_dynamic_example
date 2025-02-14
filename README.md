# flask_dynamic_example
Project that uses Flask with dynamic response


# Introduction
This application is a basic web application that uses Flask to create a web server. The application returns a JSON object that is dynamically generated. 
The JSON object is generated by a Python function that is called by the Flask application. The application is a simple example of how to create a web server that returns a dynamic response.


# Setup Python Project using UV

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

## Running Flask
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
```