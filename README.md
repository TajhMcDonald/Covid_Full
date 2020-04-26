## [Corona Myth Busters]

[![Build Status](https://travis-ci.org/AbhishekPednekar84/project-covid19.svg?branch=master)](https://travis-ci.org/AbhishekPednekar84/project-covid19) [![Coverage Status](https://coveralls.io/repos/github/AbhishekPednekar84/project-covid19/badge.svg?branch=master)](https://coveralls.io/github/AbhishekPednekar84/project-covid19?branch=master)

**Versions** 
1. Python - **3.7**
2. Django - **3.0**

**Steps to create a local setup**
1. Clone the repository - `git clone https://github.com/tajhmcdonald/covid_project`
2. Create a virtual environment - `python -m venv venv`
3. Activate the virtual environment - `venv\Sctipts\activate.bar` (Windows), `source venv/bin/activate` (OSx / Linux)
4. Install the dev / test dependencies - `pip install -r requirements-test.txt`
5. Create a `.env` file in the project root with the required environment variables (see `.env.example`)
6. In the `corona.urls` module, update the admin url - `path("update_this/", admin.site.urls),`
7. Run the database migrations -
   - `python manage.py makemigrations`
   - `python manage.py migrate`
8. Run the application - `python manage.py runserver`

**To send emails with the local setup (tested on Ubuntu 18.04)**
1. Install redis - `sudo apt install redis-server`
2. Run the redis instance - `sudo service redis-server start`
3. Update the `CELERY_BROKER_URL` environment variable in the `.env` file - `redis://localhost:6379`
4. Start a celery task queue - `celery -A worker -l info`

**To run tests** - `pytest` (Coverage will be generated as part of the test run)

**Information about some of the files in the repository**
1. Pre-commit hooks - `.pre-commit-config.yml`, `pyproject.toml` and `.flake8`
2. Continuous Integration - `.travis.yml`
3. Test coverage - `.coveragerc`
4. Pytest config - `pytest.ini`
