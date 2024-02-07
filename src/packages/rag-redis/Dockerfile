FROM python:3.11

RUN pip install poetry==1.6.1

RUN poetry config virtualenvs.create false

RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libgtk-3-0 \
    libsm6 \
    libxext6 \
    libxrender1 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY . /app

RUN poetry install --no-interaction --no-ansi --no-root

CMD ["python", "./ingest.py"]