# Organizing Configuration

Configuration management separates settings from code, making it easier to change behavior without modifying source files. Python projects typically use a combination of environment variables for secrets and configuration files for application settings.

`config.py` centralizes configuration loading and provides a single source of settings across the application:

```python
from dotenv import load_dotenv
import os

load_dotenv()  # Loads variables from .env file

class Settings:
    API_KEY: str = os.getenv('API_KEY')
    DATABASE_URL: str = os.getenv('DATABASE_URL')
    DEBUG: bool = os.getenv('DEBUG', 'False').lower() == 'true'

settings = Settings()

# Usage in other files:
# from app.config import settings
# client = APIClient(api_key=settings.API_KEY)
```

For application settings that aren't secret (model parameters, feature flags, default values), use configuration files. These can be committed to version control and make it easy to maintain different configurations for development, staging, and production.

**YAML format** (human-readable, supports nested structures):

```yaml
# config.yml
model:
  name: gpt-4
  temperature: 0.7
  max_tokens: 1000

features:
  streaming: true
  caching: false

prompts:
  system: "You are a helpful assistant"
  max_history: 10
```

```python
import yaml

with open('config.yml', 'r') as f:
    config = yaml.safe_load(f)

model_name = config['model']['name']
temperature = config['model']['temperature']
system_prompt = config['prompts']['system']
```

**INI format** (simpler, flatter structure, built into Python):

```ini
# config.ini
[model]
name = gpt-4
temperature = 0.7
max_tokens = 1000

[features]
streaming = true
caching = false
```

```python
from configparser import ConfigParser

config = ConfigParser()
config.read('config.ini')

model_name = config['model']['name']
temperature = config.getfloat('model', 'temperature')  # Automatic type conversion
max_tokens = config.getint('model', 'max_tokens')
streaming = config.getboolean('features', 'streaming')
```
