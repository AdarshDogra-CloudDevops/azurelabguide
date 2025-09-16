# Exercise 2 – Building and Pushing a Docker Image to ACR (Using Docker Desktop)

In this exercise, you will build a Docker image locally using **Docker Desktop** and then push it to **Azure Container Registry (ACR)**.

---

### 1. Start Docker Desktop
- Click the **Docker Desktop** shortcut to open it.  
- Accept the **service agreement** prompt.  
- Click **Skip** on the sign-in prompt.  
- Wait 3–4 minutes for Docker to start.  
- If a **WSL prompt** appears, close it.  
- Once Docker is running, you should see the whale 🐳 icon in the system tray.  

---

### 2. Verify Docker Installation
Open **Windows PowerShell** and run:

```powershell
docker --version
```
Expected output example:
 **Docker version 28.4.0, build d8eb465**

### 3. Create a Project Directory

```powershell
mkdir C:\DockerProjects\apache-demo
cd C:\DockerProjects\apache-demo
```

