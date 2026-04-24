# 🐳 My Container Lab Portfolio

Welcome to my personal lab repository where I document my journey learning container orchestration, security, and networking using **Podman** and **Docker**.

---

## 🏗️ Lab Entries

### 1. OWASP Juice Shop
**Description:** A purposefully insecure web application for security training. It is a modern web app written in Node.js, Express, and Angular.

#### 🚀 Running the Container
To pull the image and run the application using Podman:
```bash
podman run --rm -d \
  -p 3000:3000 \
  --name juice-shop \
  docker.io/bkimminich/juice-shop
```

#### 🌐 Accessing the Lab
- **Local:** Open your browser and navigate to `http://localhost:3000`.
- **Remote (SSH Tunneling):** If running the container on a remote VM, use an SSH tunnel to forward the port to your local machine:
  ```bash
  ssh -L 3000:localhost:3000 <your-username>@<your-remote-ip>
  ```
  Once the tunnel is active, you can access the app at `http://localhost:3000` on your local browser.

#### 🛠️ Verification
To verify the application is responding via CLI:
```bash
curl -I http://localhost:3000
```

---

## 🔧 Tools Used
- **Runtime:** Podman (Daemonless Container Engine)
- **Security:** OWASP Juice Shop
- **Networking:** SSH Tunneling / Port Forwarding

---
*Last Updated: 2026-04-24*
