
# 🚀 Flask CI/CD Pipeline Demo

This project demonstrates a **CI/CD (Continuous Integration and Continuous Deployment)** setup using **GitHub Actions** for a basic **Flask** application. The pipeline automatically runs unit tests on every push or pull request to the `main` branch.

---

## 📁 Project Structure

```
flask-ci-cd-app/
│
├── app.py                 # Main Flask app
├── requirements.txt       # Python dependencies
├── test\_app.py            # Unit tests
└── .github/
└── workflows/
└── ci-cd.yml      # GitHub Actions workflow

````

---

## 🔧 Tech Stack

- **Language:** Python 3.9  
- **Framework:** Flask  
- **CI/CD Tool:** GitHub Actions  

---

## 🛠️ Local Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/flask-ci-cd-app.git
cd flask-ci-cd-app
````

### 2. Set Up a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows use venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

The app will be live at: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

---

## 🧪 Running Unit Tests

This project uses Python’s built-in `unittest` framework. To run tests:

```bash
python -m unittest discover
```

---

## 🤖 GitHub Actions: CI/CD Workflow

GitHub Actions automates testing for this project.

### 📄 Workflow File Location

```
.github/workflows/ci-cd.yml
```

### ⚙️ Workflow Triggers

* On **push** to `main`
* On **pull request** to `main`

### 🧱 Workflow Steps

1. **Checkout** the code
2. **Set up Python 3.9**
3. **Install dependencies**
4. **Run unit tests**

### 🔍 Example Workflow

```yaml
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
```

---

## ✅ CI/CD in Action

* Push or open a pull request
* GitHub Actions will:

  * Build your app
  * Install dependencies
  * Run tests
* See results in the **Actions** tab on GitHub

---

