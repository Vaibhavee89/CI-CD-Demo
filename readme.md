🚀 Flask CI/CD Pipeline Demo
This project demonstrates a basic CI/CD (Continuous Integration & Continuous Deployment) pipeline using GitHub Actions for a Python Flask web application. It includes automatic testing and can be extended to support deployment to cloud platforms like Heroku, Render, or Docker-based VPS.

📁 Project Structure
bash
Copy
Edit
flask-ci-cd-app/
│
├── app.py                 # Main Flask app
├── requirements.txt       # Python dependencies
├── test_app.py            # Unit tests
└── .github/
    └── workflows/
        └── ci-cd.yml      # GitHub Actions workflow
🔧 Tech Stack
Language: Python 3.9

Framework: Flask

CI/CD Tool: GitHub Actions

Deployment: Optional (Heroku, Docker, etc.)

🛠️ Setup Locally
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/flask-ci-cd-app.git
cd flask-ci-cd-app
2. Set Up Virtual Environment
bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows use venv\Scripts\activate
3. Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
4. Run the Application
bash
Copy
Edit
python app.py
App will be live at http://127.0.0.1:5000/

🧪 Running Unit Tests
This project includes a simple test using Python’s built-in unittest framework.

bash
Copy
Edit
python -m unittest discover
🤖 GitHub Actions CI/CD Workflow
GitHub Actions automates the build and test process. The workflow is defined in:

bash
Copy
Edit
.github/workflows/ci-cd.yml
Workflow Triggers:
On every push or pull_request to the main branch.

Workflow Steps:
Checkout source code

Set up Python

Install dependencies

Run unit tests

Example Workflow File:
yaml
Copy
Edit
name: CI/CD Pipeline

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: 3.9

    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    - name: Run tests
      run: |
        python -m unittest discover
✅ CI/CD in Action
Push code to GitHub

GitHub Actions triggers automatically

Code is built and dependencies installed

Tests are executed

Success/failure is shown in the Actions tab