## Pipenv

```console
pipevn --python 3.6
pipenv shell
pipenv install <package_name>
pipenv lock -r > requirements.txt
pipenv install -r requirements.txt
pipenv install --dev flake8

# Create .venv in the project directory
PIPENV_VENV_IN_PROJECT=1
```
