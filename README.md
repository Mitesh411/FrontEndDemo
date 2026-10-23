# FrontEndDemo

[![sitespeed.io CI](https://github.com/mitesh411/FrontEndDemo/actions/workflows/blank.yml/badge.svg)](https://github.com/mitesh411/FrontEndDemo/actions/workflows/blank.yml)
[![Security Hardened](https://img.shields.io/badge/Security-Sentinel%20Shield%20%F0%9F%9F%A2-brightgreen)](#security)

A demonstration repository for automated web performance auditing and frontend CI workflows using **sitespeed.io** and GitHub Actions.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [CI/CD Pipeline](#cicd-pipeline)
- [Security](#security)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

---

## 🔍 Overview

**FrontEndDemo** is designed to demonstrate automated performance regression monitoring for frontend web applications. Using [sitespeed.io](https://www.sitespeed.io/), the pipeline automatically analyzes web pages against web performance best practices, measures performance metrics, and archives detailed HTML reports as workflow artifacts.

---

## ✨ Features

- **Automated Web Performance Testing:** Runs `sitespeed.io` in a Docker container on every push.
- **Artifact Archiving:** Uploads detailed test reports as workflow artifacts accessible directly from GitHub Actions runs.
- **Security-First CI:** Hardened workflow permissions adhering to the principle of least privilege.

---

## ⚙️ CI/CD Pipeline

The repository includes a GitHub Actions workflow located at `.github/workflows/blank.yml`.

### Workflow Breakdown:
1. **Code Checkout:** Checks out repository files using `actions/checkout@v4.2.0`.
2. **Directory Creation:** Prepares the `testResults` directory for report output.
3. **Sitespeed.io Analysis:** Executes the official `sitespeedio/sitespeed.io` Docker container to test target URLs.
4. **Report Upload:** Publishes the generated analysis files as a GitHub Actions artifact named `RunReports`.

---

## 🛡️ Security

This repository is monitored and secured according to **Sentinel** security guidelines:

- **Least Privilege Tokens:** GitHub Actions jobs are configured with explicit `permissions: contents: read` to restrict `GITHUB_TOKEN` scope and prevent unauthorized repository modifications.
- **No Hardcoded Secrets:** Workflow configurations do not expose API keys or sensitive credentials.

---

## 🚀 Getting Started

### Prerequisites

To run performance tests locally, ensure you have Docker installed:
- [Docker Engine / Docker Desktop](https://docs.docker.com/get-docker/)

### Running Performance Tests Locally

Execute sitespeed.io locally using Docker:

```bash
docker run --rm -v "$(pwd):/sitespeed.io" sitespeedio/sitespeed.io:35.0.0-slim https://mitesh411.github.io/MyResume/ -n 1
```

Once complete, open the generated `sitespeed-result` folder in your browser to view the HTML report.

---

## 🤝 Contributing

Contributions are welcome! Please ensure any workflow changes follow security best practices and declare explicit token permissions.

---

## 📄 License

This project is open-source under the [MIT License](LICENSE).
