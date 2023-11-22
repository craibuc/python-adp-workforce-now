# adp-workforce-now
A Python library that wraps ADP's Workforce Now API.

## Installation

## Usage

### Create a client instance
```python
from adp_workforce_now import AdpClient

import os

from dotenv import load_dotenv
load_dotenv()

client = AdpClient(os.getenv('ADP_CLIENT_ID'), os.getenv('ADP_CLIENT_SECRET'), "/path/to/certificate.pem", "./path/to/private_key.key")

client.authenticate()
```
### Get a worker
```python
worker = client.worker()

w = worker.one('ABCEDFGHIJKLMNOP')

print('legalName',w["person"]["legalName"]["formattedName"])
```

## Development
### Test
```python
python setup.py pytest
```

### Build
```python
python setup.py bdist_wheel
```

### Install
```python
pip install /dist/adp_workforce_now-{version}-py3-none-any.whl
```

## Reference
- [How to create a Python library](https://medium.com/analytics-vidhya/how-to-create-a-python-library-7d5aea80cc3f)
- [Deep dive: Create and publish your first Python library](https://towardsdatascience.com/deep-dive-create-and-publish-your-first-python-library-f7f618719e14)
- [How to Publish an Open-Source Python Package to PyPI](https://realpython.com/pypi-publish-python-package/)