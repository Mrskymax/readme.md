
```markdown
# ⚙️ Continuous Integration (CI) Workflow

This project uses GitHub Actions to automate testing and dependency management every time changes are made to the `main` branch.

## 📄 Workflow File: `.github/workflows/ci.yml`

### ✅ Workflow Name
```yaml
name: CI
```
This defines the name of the workflow as **CI**, which stands for Continuous Integration.

---

### 🔄 Trigger Events
```yaml
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
```
This workflow is triggered automatically when:
- A `push` is made to the `main` branch.
- A `pull request` is created targeting the `main` branch.

---

### 🛠 Job: `build`
```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```
This job runs in a GitHub-hosted environment using the latest version of **Ubuntu**.

---

### 🧩 Steps Breakdown

#### 1. Checkout Code
```yaml
- name: Checkout code
  uses: actions/checkout@v2
```
This step checks out the repository code so that the workflow can access it.

#### 2. Set Up Node.js
```yaml
- name: Set up Node.js
  uses: actions/setup-node@v2
  with:
    node-version: '14'
```
This sets up **Node.js version 14**, required to run your Node.js-based project.

#### 3. Install Dependencies
```yaml
- name: Install dependencies
  run: npm install
```
Installs all project dependencies using `npm`.

#### 4. Run Tests
```yaml
- name: Run tests
  run: npm test
```
Executes all tests in your project to ensure that everything is working correctly.

---

## 📌 Benefits of CI

- **Automatic Testing**: Helps catch errors early by running tests automatically.
- **Stable Codebase**: Prevents broken code from being merged into the `main` branch.
- **Improved Workflow**: Encourages smooth and reliable development practices.

---
