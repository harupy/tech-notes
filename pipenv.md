## Pipenv

```console
# Create a new virtualenv with a specific python version
pipevn --python 3.6

# Activate the Pipenv shell
pipenv shell

# Install a package
pipenv install <package_name>

# pip freeze
pipenv lock -r > requirements.txt

# Install dependencies with requirements.txt
pipenv install -r requirements.txt

# Install dev dependencies
pipenv install --dev flake8

# Create .venv in the project root
PIPENV_VENV_IN_PROJECT=1
```

[Pipenv: Python Dev Workflow for Humans — pipenv 2018.11.27.dev0 documentation](https://docs.pipenv.org/en/latest/)
