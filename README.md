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

---

## 🧠 Core Concepts (For Beginners)

### 🚪 What is Port Mapping? (`-p 3000:3000`)
When you run a container, it lives in its own "private island" (a isolated environment). By default, you can't see what's happening inside.

**Think of it like a hotel:**
- The **Container** is like a hotel room. Inside that room, the website is playing on a TV (Port 3000).
- Your **Computer** is the hotel building.
- The command `-p 3000:3000` creates a **door** from the outside world (your computer's port 3000) directly into that specific room's TV (the container's port 3000).

Without the `-p` flag, the "door" is locked, and you wouldn't be able to see the website in your browser at `localhost:3000`.

### 🌍 How is this website maintained for everyone?
The OWASP Juice Shop is an **Open Source** project. Instead of hosting one giant website that everyone logs into (which would be expensive and hard to manage), the owners do something smarter:

1. **The Blueprint (Image):** The owner writes the code and turns it into a "Container Image" (a blueprint).
2. **The Library (Docker Hub):** They upload this blueprint to a public library called **Docker Hub** (`docker.io`).
3. **Your Copy:** When you run the `podman` command, you are downloading a **perfect copy** of that blueprint to your own machine. 

This allows the owner to update the "blueprint" once, and everyone in the world can instantly get the latest version for their own private study lab.

---

## 🌐 Accessing the Lab
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
- **Registry:** Docker Hub (Image hosting)
- **Networking:** SSH Tunneling / Port Forwarding

---
*Last Updated: 2026-04-24*
