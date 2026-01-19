# CI/CD Pipeline – DevOps Workflow (GitHub Actions)

In this project, I implemented a **CI/CD pipeline** using **GitHub Actions** to follow DevOps best practices. The pipeline automates **code validation, containerization, and deployment**, ensuring that every change is tested, reliable, and production-ready.

This workflow supports:
- **Continuous Integration (CI)** – automated linting, testing, and container builds
- **Continuous Delivery (CD)** – automated deployment to GitHub Pages

---

## 🔁 Pipeline Triggers

I configured the pipeline to run automatically when changes are made to critical parts of the project.

### Pull Requests to `main`
The CICD pipeline runs when a pull request targets the `main` branch and includes changes in:
- `chap4/**`
- `site/**`
- `.github/workflows/cicd.yaml`

This allows me to validate code quality **before merging**, which aligns with DevOps shift-left testing practices.

### Pushes to `main`
On direct pushes to `main`, the pipeline:
- Runs CI validation
- Builds and pushes a Docker image
- Deploys the static site to GitHub Pages

---

## 🔐 Security & Access Control

I applied the principle of **least privilege** by assigning only the required permissions:

- `contents: read` – access repository content
- `pages: write` – deploy artifacts to GitHub Pages
- `id-token: write` – enable secure authentication for deployments

---


## 🚀 Live Deployment (GitHub Pages)

<img width="875" height="217" alt="github-pages-deployed" src="https://github.com/user-attachments/assets/a0fb5d24-fb3b-44f0-a6ac-5440572a48c6" />


This screenshot verifies that the **Continuous Deployment (CD)** stage is working correctly.
Once CI passes on the `main` branch, the site is automatically deployed.


