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
