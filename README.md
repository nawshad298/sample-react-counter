ample React Counter with Docker

A simple, interactive React Counter application containerized using a multi-stage Docker build and served via an optimized Nginx web server.

## 🚀 Features
* **React Frontend:** Lightweight and responsive interactive counter.
* **Production Ready:** Built with a multi-stage Dockerfile to drastically reduce final image size using `node:18-alpine` and `nginx:alpine`.
* **Nginx Web Server:** High-performance serving of production static assets.

---

## 🛠️ Prerequisites
Before running or building this project, ensure you have the following installed:
* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/) (optional, only for local development)
* [Docker](https://www.docker.com/)

---

## 💻 Local Development (Without Docker)

1. **Clone the repository:**
```bash
   git clone [https://github.com/YOUR_GITHUB_USERNAME/sample-react-counter.git](https://github.com/YOUR_GITHUB_USERNAME/sample-react-counter.git)
   cd sample-react-counter
