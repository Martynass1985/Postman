<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/c2/Postman_%28software%29.png" alt="Postman Logo" width="200">
</p>

<h1 align="center">🚀 Automation Exercise API Tests</h1>

<p align="center">
  This repository contains API tests for the Automation Exercise platform, implemented using Postman and executed via GitHub Actions.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Postman-API%20Testing-orange?style=for-the-badge&logo=postman" alt="Postman Badge">
  <img src="https://img.shields.io/badge/CI-GitHub%20Actions-blue?style=for-the-badge&logo=githubactions" alt="GitHub Actions Badge">
  <img src="https://img.shields.io/badge/Reports-HTML-green?style=for-the-badge&logo=html5" alt="HTML Reports Badge">
</p>

---

<p align="center">
  <a href="https://www.automationexercise.com/api_list" target="_blank">
    <img src="https://www.automationexercise.com/static/images/home/logo.png" alt="Automation Exercise">
  </a>
</p>

---

## 📚 Table of Contents

- [📚 Table of Contents](#-table-of-contents)
- [✨ Features](#-features)
- [📋 Prerequisites](#-prerequisites)
- [⚙️ Installation](#️-installation)
- [▶️ How to Run](#️-how-to-run)
  - [Locally](#locally)
  - [CI/CD (GitHub Actions)](#cicd-github-actions)
- [🛠️ Setup Tests](#️-setup-tests)
- [📂 Project Structure](#-project-structure)
- [📝 Example Tests](#-example-tests)
  - [Test Case: Verify Login without Email Parameter](#test-case-verify-login-without-email-parameter)
  - [Test Case: Delete User Account](#test-case-delete-user-account)
- [📜 License](#-license)
- [📧 Contact](#-contact)

---

## ✨ Features

- ✅ Automated API testing using Postman collections.
- 🔄 Continuous integration with GitHub Actions.
- 📊 HTML test reports generated with Newman.
- 🌐 Environment variables for flexible test configuration.

---

## 📋 Prerequisites

- 🖥️ [Node.js](https://nodejs.org/) (version 18 or higher)
- 🐙 GitHub account (for running tests via GitHub Actions)

---

## ⚙️ Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

---

2. Install dependencies:
   ```sh
   npm install
   ```

---

## ▶️ How to Run

### Locally

Run the Postman collection using Newman:

```sh
npx newman run

AutomationExercise.postman_collection.json

 \
  --environment

environment.json

 \
  --reporters cli,html \
  --reporter-html-export newman/report.html
```

### CI/CD (GitHub Actions)

Push your changes to the `main` branch or create a pull request. The GitHub Actions workflow defined in [`.github/workflows/postman-test.yml`](.github/workflows/postman-test.yml) will automatically execute the tests and upload the HTML report as an artifact.

---

## 🛠️ Setup Tests

1. Update the environment variables in [Postman/environment.json](Postman/environment.json) with your API base URL and other required values.
2. Modify the Postman collection in [Postman/AutomationExercise.postman_collection.json](Postman/AutomationExercise.postman_collection.json) to add or update test cases.

---

## 📂 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── postman-test.yml       # GitHub Actions workflow for running tests
├── Postman/
│   ├── AutomationExercise.postman_collection.json  # Postman collection
│   ├── environment.json          # Postman environment variables
├──

package.json

                  # Project dependencies
└──

README.md

                     # Project documentation
```

---

## 📝 Example Tests

### Test Case: Verify Login without Email Parameter

```javascript
pm.test("Response has responseCode and message", function () {
  const responseData = pm.response.json();
  pm.expect(responseData).to.be.an("object");
  pm.expect(responseData.responseCode).to.be.a("number").and.to.be.eq(400);
  pm.expect(responseData.message)
    .to.be.a("string")
    .and.to.be.eq(
      "Bad request, email or password parameter is missing in POST request."
    );
});
```

### Test Case: Delete User Account

```javascript
pm.test("Response has responseCode and message", function () {
  const responseData = pm.response.json();
  pm.expect(responseData).to.be.an("object");
  pm.expect(responseData.responseCode).to.be.a("number").and.to.be.eq(200);
  pm.expect(responseData.message)
    .to.be.a("string")
    .and.to.be.eq("Account deleted!");
});
```

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 📧 Contact

For questions or feedback, please contact:

- **Name:** Martynas
- **Email:** marat19@gmail.com
- **GitHub:** [your-username](https://github.com/Martynass1985)

---
