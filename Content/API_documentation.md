
# GitHub API – Documentation Overview

This document provides an overview of the GitHub REST API endpoints used for this assignment, including usage, parameters, and expected responses.

---

## 🔍 1. Search Repositories

**Endpoint:**
```
GET /search/repositories
```

**Description:**
Searches for public repositories based on a query string.

**Example Request:**
```
GET https://api.github.com/search/repositories?q=machine+learning&per_page=5
```

**Parameters:**
- `q`: Search keywords (required).
- `sort`: stars, forks, or updated (optional).
- `order`: asc or desc (optional).
- `per_page`: Number of results per page (default: 30, max: 100).

**Response Sample:**
```json
{
  "total_count": 123456,
  "items": [
    {
      "full_name": "scikit-learn/scikit-learn",
      "stargazers_count": 56000,
      "language": "Python",
      ...
    }
  ]
}
```

---

## 📜 2. List Repository Commits

**Endpoint:**
```
GET /repos/{owner}/{repo}/commits
```

**Description:**
Lists commits on a repository.

**Example Request:**
```
GET https://api.github.com/repos/scikit-learn/scikit-learn/commits?per_page=5
```

**Parameters:**
- `sha`: The SHA or branch to start listing commits from.
- `path`: Only commits containing this file path will be returned.
- `author`: GitHub username or email to filter commits.
- `per_page`: Number of results per page.

**Response Sample:**
```json
[
  {
    "sha": "abc123...",
    "commit": {
      "author": {
        "name": "John Doe",
        "date": "2023-05-15T10:15:30Z"
      },
      "message": "Fix issue with model training"
    }
  }
]
```

---

## 📂 3. Get Repository Contents

**Endpoint:**
```
GET /repos/{owner}/{repo}/contents/{path}
```

**Description:**
Gets the contents of a file or directory in a repository.

**Example Request:**
```
GET https://api.github.com/repos/scikit-learn/scikit-learn/contents/
```

**Response Sample:**
```json
[
  {
    "name": "README.md",
    "type": "file",
    "download_url": "https://raw.githubusercontent.com/.../README.md"
  },
  {
    "name": "examples",
    "type": "dir",
    "url": "https://api.github.com/repos/.../contents/examples"
  }
]
```

---

## 🔐 Authentication

Use a personal access token (PAT) for authentication.

**Header format:**
```
Authorization: Bearer <your_token>
```

**API Version Header (recommended):**
```
X-GitHub-Api-Version: 2022-11-28
```

---

## 🔄 Pagination

Use `per_page` and `page` query parameters to handle pagination.

**Example:**
```
GET /search/repositories?q=data&page=2&per_page=100
```

---

## 📉 Rate Limits

Authenticated requests: 5000/hour  
Unauthenticated requests: 30/hour

**Check limits via headers:**
- `X-RateLimit-Limit`
- `X-RateLimit-Remaining`
- `X-RateLimit-Reset`

---
