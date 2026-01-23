FROM python:3.12-slim

WORKDIR /app

RUN apt-get update \
    && apt-get -y install libpq-dev gcc \
    && pip install psycopg2
COPY . .


RUN pip install -r ./requirements.txt
# We still need this historically used -e option (editable mode) for the imports.
# This may not be the best method for installing, but this project is also old, so close enough.
RUN pip install -e .


# Configuration via environment
ENV GUNICORN_WORKERS=2
ENV GUNICORN_BIND=0.0.0.0:8000

CMD gunicorn app:app \
    --workers ${GUNICORN_WORKERS} \
    --bind ${GUNICORN_BIND} \   
    --paste ./development.ini