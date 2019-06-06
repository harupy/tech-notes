## Read a JSON file

```python
def read_json(filepath):
  with open(filepath, 'r') as f:
    return json.load(f)
```

## Logger Function

- [Basic example on how setup a Python logger](https://gist.github.com/nguyenkims/e92df0f8bd49973f0c94bddf36ed7fd0)
- [Python Logging: In-Depth Tutorial | Toptal](https://www.toptal.com/python/in-depth-python-logging)

```python
import logging
import sys
import os


FORMATTER = logging.Formatter("%(asctime)s - %(name)s - %(levelname)s - %(message)s")
LOG_DIR = 'logs'
LOG_FILE = f'{LOG_DIR}/app.log'


def log_init():
  if not os.path.exists(LOG_DIR):
    os.mkdir(LOG_DIR)


def get_stream_handler():
  stream_hanlder = logging.StreamHandler(sys.stdout)
  stream_hanlder.setFormatter(FORMATTER)
  stream_hanlder.setLevel(logging.DEBUG)
  return stream_hanlder


def get_file_handler():
  file_handler = logging.FileHandler(LOG_FILE, mode='a')
  file_handler.setFormatter(FORMATTER)
  file_handler.setLevel(logging.INFO)
  return file_handler


def get_logger(logger_name):
  logger = logging.getLogger(logger_name)
  logger.setLevel(logging.INFO)
  logger.addHandler(get_stream_handler())
  logger.addHandler(get_file_handler())
  logger.propagate = False

  return logger

```

## Python Logger Starter

```python
import os
from logging import getLogger, Logger, StreamHandler, FileHandler, Formatter, DEBUG

LOG_DIR = 'logs'

if not os.path.exists(LOG_DIR):
  os.mkdir(LOG_DIR)

logger: Logger = getLogger(__name__)
stream_handler: StreamHandler = StreamHandler()
fmt = '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
formatter: Formatter = Formatter(fmt)
stream_handler.setFormatter(formatter)
file_handler: FileHandler = FileHandler(filename=os.path.join(LOG_DIR, f'{__name__}.log'), mode='w')
stream_handler.setLevel(DEBUG)
file_handler.setLevel(DEBUG)
logger.setLevel(DEBUG)
logger.addHandler(stream_handler)
logger.addHandler(file_handler)
logger.propagate = False


logger.critical('critical')
logger.error('error')
logger.warning('warning')
logger.info('info')
logger.debug('debug')
```
