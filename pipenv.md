# pipenv

## Commands

| Command                             | Action                                                 |
| ----------------------------------- | ------------------------------------------------------ |
| pipenv --python x.x                 | create a new virtualenv with a specific python version |
| pipenv shell                        | activate the pipenv shell                              |
| pipenv install <package_name>       | install a package                                      |
| pipenv rock -r > requirements.txt   | save dependencies to requirements.txt                  |
| pipenv install -r requirements.txt  | install dependencies with requirements.txt             |
| pipenv install --dev <package_name> | install dev dependency                                 |

[Pipenv: Python Dev Workflow for Humans — pipenv 2018.11.27.dev0 documentation](https://docs.pipenv.org/en/latest/)

## Create _.venv_ directory in the project root

`~/.zshrc` or `~/.bash_profile`

```bash
export PIPENV_VENV_IN_PROJECT=1
```

`settings.json` in vscode

```json
{
  "python.venvPath": ".venv",
  "python.pythonPath": "${workspaceFolder}/.venv/bin/python"
}
```

## Jupyter with pipenv

### Method 1

```console
pipenv install ipykernel
pipenv shell

python -m ipykernel install --user --name=my-virtualenv-name
jupyter notebook
```

[python - Is there a way to use pipenv with Jupyter notebook? - Stack Overflow](https://stackoverflow.com/questions/47295871/is-there-a-way-to-use-pipenv-with-jupyter-notebook)

### Method 2

Initial Setup

```console
# generate ~/.jupyter/jupyter_notebook_config.py
pipenv run jupyter notebook --generate-config

# add new configurations
echo 'c.NotebookApp.contents_manager_class = "jupyter.text.TextFileContentsManager"' >> ~/.jupyter/jupyter_notebook_config.py
echo 'c.ContentsManager.default_jupytext_formats = "ipynb,py"' >> ~/.jupyter/jupyter_notebook_config.p
```

Initialize a project

```console
mkdir project_dir
cd project_dir

pipenv install jupyter jupytext
```

Run a notebook

```console
pipenv run jupyter notebook
```

[Pipenv を使って Jupyter Notebook を導入する方法 - Qiita](https://qiita.com/SUZUKI_Masaya/items/76b927b9812d77d33e57)
