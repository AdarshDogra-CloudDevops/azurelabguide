# Lab 2 – Creating an Azure Container Registry (ACR)

1. In the Azure Portal, search for **Container Registries** → Click **Create**.  
![](./azurelab/cr1.png)
2. Fill in the details:
   - **Resource Group**: Use the resource group provided in your lab environment.  
   - **Registry Name**: `myacr1234`  
   ![](./azurelab/cr2.png)
   - **Location**: East US  
   - **Pricing Plan**: Basic  
   - Leave other settings as default.  
![](./azurelab/cr3.png)
4. Click **Review + Create** → **Create**.  
![](./azurelab/cr4.png)
Once the deployment is complete, your ACR is created.  

4. Click **Go to Resource** to open your ACR (`myacr1234`).  
![](./azurelab/cr5.png)
5. In the left menu, click **Access Keys**.  
![](./azurelab/cr6.png)
6. Enable **Admin User = Enabled**.  
![](./azurelab/cr7.png)
You will now see:  
- **Username**  
- **Password1** and **Password2**  

These credentials are required to pull/push images from the registry.
