
# 🚀 Dockerized React Frontend

This project shows how to run a **React.js frontend application** inside a **Docker container** and serve it in **production mode** using **Nginx**.
It uses a **multi-stage Docker build** for better performance, security, and smaller image size.

---

## 🛠 Technologies Used

* React.js
* Docker
* Nginx
* Node.js

---

 📁 Project Structure

```
ecommerce-site/
├── src/
├── public/
├── package.json
├── Dockerfile
└── README.md
```

---

🐳 Docker Architecture

This project uses **multi-stage Docker build**:

🔹 Stage 1 – Build

* Node.js image is used
* Dependencies are installed
* React app is built using `npm run build`

🔹 Stage 2 – Production

* Nginx image is used
* React build files are copied
* Nginx serves the static files

This makes the final container **small, fast, and production-ready**.

---

⚠️ OpenSSL Fix for Node.js

Modern Node.js versions (17+) use OpenSSL 3, which breaks older React/Webpack builds.
This project fixes that by using:

```
NODE_OPTIONS=--openssl-legacy-provider
```

inside the Dockerfile.



 ▶ How to Run the Project

1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2️⃣ Build Docker Image

```bash
docker build -t react-app .
```

3️⃣ Run the Container

```bash
docker run -d -p 3000:80 --name react-container react-app
```

 4️⃣ Open in Browser

```
http://localhost:3000
```

Your React app will now be running inside Docker and served by Nginx.

---

🧪 Useful Docker Commands

Check running containers:

```bash
docker ps
```

Stop the container:

```bash
docker stop react-container
```

Remove the container:

```bash
docker rm react-container
```

---

📚 What This Project Demonstrates

* React production build
* Docker multi-stage builds
* Nginx static hosting
* Containerized frontend deployment
* Handling Node.js OpenSSL issues

---

👨‍💻 Author

Suyash Singh
