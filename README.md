# RELATE for docker compose

## Edit local_settings.py

Edit setting file if needed.

```python
ALLOWED_HOSTS = [
        "localhost",
        ]

# Configure the following as url as above.
RELATE_BASE_URL = "http://localhost"
```

## Building

```
docker-compose build
```

## Start

```
docker-compose up -d
```