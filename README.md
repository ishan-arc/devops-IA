# Selenium DevOps Case Study

This project demonstrates how to integrate Selenium UI tests into a DevOps CI/CD pipeline using GitHub Actions.

## Project Purpose

The main goal of this project is to showcase a practical example of running automated Selenium tests as part of a continuous integration (CI) workflow. This ensures that UI functionalities are automatically verified on every code change, improving software quality and enabling faster release cycles.

The test in this project automates a login sequence on `the-internet.herokuapp.com`, a website designed for testing automation.

## How to Run Tests Locally

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/selenium-devops-case-study.git
    cd selenium-devops-case-study
    ```

2.  **Create a virtual environment and activate it:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the tests:**
    You will need to have Google Chrome installed on your machine.
    ```bash
    python -m unittest discover -s tests
    ```

## GitHub Actions Workflow

The CI workflow is defined in `.github/workflows/selenium-tests.yml` and runs automatically on every `push` and `pull_request` to the `main` branch.

The workflow performs the following steps:
1.  **Checks out the code:** It clones the repository into the runner.
2.  **Sets up Python:** It configures a Python 3.10 environment.
3.  **Installs dependencies:** It installs Selenium and other required packages from `requirements.txt`.
4.  **Sets up Chrome:** It uses the `browser-actions/setup-chrome` action to install Google Chrome in the runner.
5.  **Runs Selenium tests:** It executes the tests located in the `tests` directory.

This automated process helps in catching UI bugs early and ensures that the application remains stable.
