# Data-Source-API-Analyst-Test

## 🔍 Objective

The main goals of this assignment are:

- Understand and identify relevant endpoints in the GitHub API.
- Extract repository, commit, and content information.
- Handle authentication, rate limiting, and pagination.

This was done using a Google Colab notebook.

## 📁 Repository Structure
Data-Source-API-Analyst-Test/
├── README.md
├── Content/
│ ├── API_documentation.md
│ ├── api_requests.ipynb
│ └── Troubleshooting_guide.md

Data-Source-API-Analyst-Test/
├── README.md
├── Content/
│   ├── API_documentation.md
│   ├── api_requests.ipynb      
│   └── Troubleshooting_guide.md

## ✅ API Endpoints Used

- `GET /search/repositories` – Search for repositories
- `GET /repos/{owner}/{repo}/commits` – List commits
- `GET /repos/{owner}/{repo}/contents/{path}` – Access repository contents


## ⚙️The Colab notebook contains:

- Setup and authentication logic
- Function-based API requests for each endpoint
- Pagination and error handling
- Print samples of responses for validation