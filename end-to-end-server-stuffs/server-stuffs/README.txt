server-stuffs README
==================

Getting Started (out of date for sure)
---------------

- cd <directory containing this file>

- $VENV/bin/pip install -e .

- $VENV/bin/alembic upgrade head

- $VENV/bin/pserve development.ini

## Docker compose setup
`docker compose up` should now work, ezpz.

Things to account for:
- frontend is served by Nginx still, not yet via docker compose.
- AWS creds need to be passed in.

