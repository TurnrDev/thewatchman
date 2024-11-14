# Getting Started

Step 1: Create a virtual environment to install dependencies:
```bash
python3 -m venv venv
source venv/bin/activate
```
Warning: if virtual environment was not set up, some tests may fail.

Step 2: install the dependencies that will allow you to run tests:
`pip3 install -r requirements_test.txt.`

This will install `homeassistant`, `pytest`, and `pytest-homeassistant-custom-component`, a plugin which allows you to leverage helpers that are available in Home Assistant for core integration tests.
If you change the version of HA it is recommended to reinstall test dependencies before running tests.

Step 3: Run `pytest tests/` to run all tests.

# Useful commands

Command | Description
------- | -----------
`pytest tests/` | This will run all tests in `tests/` and tell you how many passed/failed
`pytest --durations=10 --cov-report term-missing --cov=custom_components.integration_blueprint tests` | This tells `pytest` that your target module to test is `custom_components.integration_blueprint` so that it can give you a [code coverage](https://en.wikipedia.org/wiki/Code_coverage) summary, including % of code that was executed and the line numbers of missed executions.
`pytest tests/test_init.py -k test_setup_unload_and_reload_entry` | Runs the `test_setup_unload_and_reload_entry` test function located in `tests/test_init.py`

# Troubleshooting
If all of some tests fail, you may need to remove venv folder and perform steps from getting started again.