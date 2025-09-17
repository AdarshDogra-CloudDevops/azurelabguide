# Exercise 3 – Deploying the Container Instance
**In this exercise, you will deploy your custom container image from ACR to an Azure Container Instance (ACI). You will configure networking and validate that the container is running successfully.**

1. In the Azure Portal, search for **Container Instances** → Click **Create**.  
   ![](./azurelab/ci1.png)  

2. Fill in the details:  
   - **Resource Group**: Use the default RG provided.  
   - **Container Name**: `myapache-container`  
   - **Region**: East US  
   ![](./azurelab/ci2.png)  

   - **Image Source**: Azure Container Registry  
   - **Registry**: Select `myacr1234`  
   - **Image**: `myapache:v1`  
   - **OS Type**: Linux  
   - **Size**: Leave default (1 vCPU, 1.5GB RAM)  
   ![](./azurelab/ci3.png)  

3. Networking:  
   - **DNS Name Label**: `myapachecontainer` (must be unique).  
   - **Port**: 80  
   ![](./azurelab/moni.png)  

4. Monitoring:
   In the Monitoring tab (do not enable diagnostics).
   uncheck the box
   ![](./azurelab/moni1.png)
   
5. Click **Review + Create** → **Create**.  
   ![](./azurelab/moni.png)  

6. Wait for the deployment to complete.  
   ![](./azurelab/ci6.png)  

✅ Now your deployment is complete. Click **Go to resource** to view your container instance, which should now be running and accessible.
