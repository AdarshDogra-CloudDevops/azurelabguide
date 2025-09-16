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

### 4. Create a Dockerfile

```powershell
@"
FROM httpd:2.4
COPY ./index.html /usr/local/apache2/htdocs/index.html
"@ | Out-File -FilePath Dockerfile -Encoding utf8 -Force
```

### 5. Create an index.html

```powershell
@"
<html>
  <head><title>Hello World</title></head>
  <body><h1>Hello World from Container!</h1></body>
</html>
"@ | Out-File -FilePath index.html -Encoding utf8 -Force
```

### 6. Verify Files

Expected files:
**Dockerfile** and 
**index.html**

### 7. Build the Docker Image

```powershell
docker build -t myapache:v1 .
```

**Check that the image was created:**
```powershell
docker images
```

### 8. Run & Test Locally

```powershell
docker run -d -p 8080:80 myapache:v1
```

Now open 👉 http://localhost:8080
 in your browser.
You should see the Hello World page 🎉.
 **Note:**  This is opened as localy using your system not n azure now we will push this image to ACR.

 ### 9. Push Image to ACR

 Login to your ACR:

 ```powershell
 az acr login --name myacr1234
 ```
Enter the Username and Password from the ACR Access Keys section (enabled earlier).

Tag the image for ACR:

```powershell
docker tag myapache:v1 myacr1234.azurecr.io/myapache:v1
```

Push the image:

```powershell
docker push myacr1234.azurecr.io/myapache:v1
```

✅ Your Docker image is now built locally and stored in Azure Container Registry.

 

