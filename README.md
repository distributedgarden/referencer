# referencer
Question-answering with citations

# Usage
- set environment variables
```
export OPENAI_API_KEY=...
```
- add a reference text to the `data/resource` directory
```
> docker-compose up
```


# Development Setup
- poetry, pre-commit
```
> python3 -m venv env
> source enb/bin/activate
> python3 -m pip install -r requirements
```

## tests
...

## pre-commit hooks
```
> pre-commit install
> pre-commit autoupdate
> pre-commit run --all-files
```