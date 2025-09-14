# Lab 3 – Using Cloud Shell to Prepare Docker Build Files

1. In the Azure Portal, click the **Cloud Shell** icon.  
![](./azurelab/cr6-Copy1.png)
2. In the **Welcome to Azure Cloud Shell** window, choose **Bash**.  
3. In the Getting Started window:  
   - Select **Mount Storage Account**.  
   - Choose the default subscription → Click **Apply**.  
   - On the **Mount Storage Account** screen, choose **We will create a storage account for you** → Click **Next**.  
   - Wait 2–3 minutes for deployment to complete.  

4. Once the deployment finishes, the Cloud Shell will be ready.  
   - Maximize the Cloud Shell window using the maximize button in the CloudShell bar.  

5. Create a working directory:  
   ```bash
   mkdir apache-demo
   cd apache-demo
   
6. Create a Dockerfile:
   ```bash
   cat <<EOF > Dockerfile
   FROM httpd:2.4
   COPY ./index.html /usr/local/apache2/htdocs/index.html
   EOF
   
7. Create an index.html file:
   bash```
   cat <<EOF > index.html
   <html>
   <head><title>Hello World</title></head>
   <body><h1>Hello World from Azure Container!</h1></body>
   </html>
   EOF
   
8.Build and push the image to ACR:
az acr build --registry myacr1234 --image myapache:v1 .

