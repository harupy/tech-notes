# Anaconda

## Commands

| Command                              | Action                                        |
| ------------------------------------ | --------------------------------------------- |
| conda activate <env_name>            | activate environment                          |
| conda deactivate                     | deactivate environment                        |
| conda info -e                        | list environments                             |
| conda create -n <env_name>           | create a new environment                      |
| conda remove --name <env_name> --all | remove environment                            |
| conda clean --all -y                 | Remove unused packages and caches             |
| conda env create -f env.yaml         | Create the environment from the env.yaml file |
| conda env export > env.yaml          | Export your active environment to a new file  |

[Managing environments — conda 4.7.1.post5+a18b5a3d documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#exporting-the-environment-file)

## _conda activate_ vs _source activate_

[Python Anaconda: should I use `conda activate` or `source activate` in linux - Stack Overflow](https://stackoverflow.com/questions/49600611/python-anaconda-should-i-use-conda-activate-or-source-activate-in-linux)

> As of conda 4.4, conda activate is the preferred way to activate an environment.
