# referencer
Question-answering with citations

# Table of Contents
- [Setup](#setup)
  - [Environment](#environment)
  - [Initial setup](#initial-setup)
- [Usage](#usage)
  - [Start App](#start-app)
  - [Interact](#interact)
- [Development Setup](#development-setup)
  - [tests](#tests)
  - [pre-commit hooks](#pre-commit-hooks)


# Setup 

## Environment
### set the required environment variables
```
export OPENAI_API_KEY=...

# redis image defaults
export REDIS_HOST=localhost
export REDIS_PORT=6379
export REDIS_USER=default
export REDIS_PASSWORD=password
```

### set **optional** environment variables
```
# tracing and monitoring with langsmith
export LANGCHAIN_TRACING_V2=true
export LANGCHAIN_ENDPOINT="https://api.smith.langchain.com"
export LANGCHAIN_API_KEY="<your-api-key>"
export LANGCHAIN_PROJECT="referencer"

```

## Initial Setup
Add reference pdf text(s) to the `data/resource` directory
```
# ingest the data resources
> docker-compose --profile ingest up

# let ingest complete and exit 0 then start the app
# this command is all that is required after initial setup
> docker-compose --profile app up
``` 

# Usage
## Start App
Make sure to complete the initial setup first. `docker-compose` will handle running the app and vector db locally.
```
> docker-compose --profile app up
```

## Interact 
- `http://localhost:8080/referencer/playground`: the app
- `http://localhost:8080/docs`: the API spec detected by FastAPI.


# Development Setup
- `poetry`: installed with `requirements.txt`. Used to manage the application dependencies. Make sure to add any new dependencies with poetry, e.g. `poetry add <package>`
- `pre-commit`: installed with `requirements.txt`. Applies formatting on commit.
- `yamlfmt`: yaml formatter; https://github.com/google/yamlfmt

```
> python3 -m venv env
> source enb/bin/activate
> python3 -m pip install -r requirements
```

## Tests
...

## pre-commit hooks
```
> pre-commit install
> pre-commit autoupdate
> pre-commit run --all-files
```