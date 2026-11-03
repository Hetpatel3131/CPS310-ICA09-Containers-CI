# CPS 310 — ICA09: Containers and Continuous Integration

This project reads support tickets from a CSV file and prints the total,
open, and high-priority ticket counts.

## Run locally on macOS

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
python3 -m pip install -r requirements.txt
```

Run the application:

```bash
python3 app.py
```

Run the tests:

```bash
python3 -m pytest -v
```

## Run with Docker

Start Docker Desktop before using these commands.

Build the image:

```bash
docker build -t cps310-ticket-summary .
```

Run the application:

```bash
docker run --rm cps310-ticket-summary
```

Run the tests inside a container:

```bash
docker run --rm cps310-ticket-summary python -m pytest -v
```

## Continuous integration

The workflow is located at `.github/workflows/tests.yml`.

GitHub Actions runs the tests on pushes and pull requests.
It prepares Python 3.12, installs the dependencies, and runs pytest.

Results are available in the repository's Actions tab.