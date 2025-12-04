![Catty Logo](static/img/logos/catty-100px.png)

# Catty: The Reminders App

*Catty* is a small demo web app for tracking reminders
It uses:

* [Python](https://www.python.org/) as the main programming language
* [FastAPI](https://fastapi.tiangolo.com/) for the backend
* [HTMX](https://htmx.org/) 1.8.6 for handling dynamic interactions (instead of raw JavaScript)
* [Jinja templates](https://jinja.palletsprojects.com/en/3.1.x/) with HTML and CSS for the frontend
* [TinyDB](https://tinydb.readthedocs.io/en/latest/index.html) for the database
* [Playwright](https://playwright.dev/python/) and [pytest](https://docs.pytest.org/) for testing

## Installing dependencies

You will need a recent version of Python to run this app.
To install project dependencies:

```
pip install -r requirements.txt
```

It is recommended to install dependencies into a [virtual environment](https://docs.python.org/3/library/venv.html).


## Running the app

To run the app:

```
uvicorn app.main:app --reload --host 0.0.0.0 --port 8181
```

Then, open your browser to [`http://127.0.0.1:8181`](http://127.0.0.1:8181) to load the app.



## Logging into the app

The [`config.json`](config.json) file declares the users for the app.
You may use any configured user credentials, or change them to your liking.

## Setting the database path

The app uses TinyDB, which stores the database as a JSON file.
The default database filepath is `reminder_db.json`.
You may change this path in [`config.json`](config.json).
If you change the filepath, the app will automatically create a new, empty database.


## Using the app

Catty is a reminders app.
After you log in, you can create reminder lists.

![Catty login](static/img/readme/catty-login.png)

Each reminder list appears on the left,
and the items in the list appear on the right.
You may add, delete, or edit lists and items.
You may also strike out completed items.

![Catty reminders](static/img/readme/catty-reminders.png)


## Running tests

The app includes comprehensive tests using pytest and Playwright. Before running tests, make sure the app is running on `http://127.0.0.1:8181`.

First, install test dependencies if you haven't already:

```bash
pip install -r requirements.txt
```

Install Playwright browsers for UI testing:

```bash
playwright install --with-deps chromium
```

Then configure test settings in `inputs.json`:

```json
{
  "base_url": "http://127.0.0.1:8181",
  "users": [
    {
      "username": "heisenberg",
      "password": "P@ssw0rd"
    },
    {
      "username": "tester", 
      "password": "foobar123"
    }
  ]
}
```

Run all tests:

```bash
python3 -m pytest
```

Run specific test types:

```bash
# Unit tests only
python3 -m pytest tests/test_unit.py

# API tests only  
python3 -m pytest tests/test_api.py

# UI tests only
python3 -m pytest -s -v --browser chromium tests/test_ui.py
```

Run tests with verbose output:

```bash
python3 -m pytest -v --browser chromium tests
```

## Reading the docs

To read the API docs, open the following pages:

* [`/docs`](http://127.0.0.1:8181/docs) for classic OpenAPI docs
* [`/redoc`](http://127.0.0.1:8181/redoc) for more modern ReDoc docs
# Test deployment Wed Dec  3 01:55:29 PM UTC 2025
# Test deployment Wed Dec  3 02:18:37 PM UTC 2025
# Test deployment Wed Dec  3 02:19:32 PM UTC 2025
# Test deployment 2 Wed Dec  3 02:27:49 PM UTC 2025
# Final test Wed Dec  3 02:34:45 PM UTC 2025
# Test Wed Dec  3 02:37:41 PM UTC 2025
# Test Thu Dec  4 01:27:18 PM UTC 2025
# Test Thu Dec  4 01:32:43 PM UTC 2025
# test Thu Dec  4 01:44:46 PM UTC 2025
# test Thu Dec  4 01:48:01 PM UTC 2025
# test Thu Dec  4 02:02:01 PM UTC 2025
# test Thu Dec  4 02:22:17 PM UTC 2025
# test Thu Dec  4 02:30:29 PM UTC 2025
