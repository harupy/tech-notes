# Doctest

## Basic

utils.py

````python
def hello():
  """
  Print out 'hello'

  Example:
  >>> hello()
  'hello'
  """

  return 'hello'

if __name__ == '__main__':
  import doctest
  doctest.testmod(verbose=True)


```console
python utils.py
````
