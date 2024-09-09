# Quest 1 - Buckle up!

**[🏠Home](../README.md)** - [ Quest 2 >](quest2.md)

In this tutorial, you will perform basic deployments to set up your environment for the hands-on lab. 

## Pre-Requisites and Installation for hands-on lab

* Create an Azure OpenAI resource, if not created already. Follow the steps [here](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/create-resource)

> [!TIP]
> If you already created an Azure OpenAI resource, you may be able to use it.

* Deploy a vision-capable model. Examples include, GPT-4T-0125, GPT-4T-0409 or GPT-4-Omni.
* Make sure you are able to create Azure Document Intelligence service in a region which supports markdown feature.  
* Create a Log Analytics Workspace in the target Azure region and make a note of its resource ID. 
* Install azd CLI. Follow the steps [here](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/install-azd?tabs=winget-windows%2Cbrew-mac%2Cscript-linux&pivots=os-linux)  
* Enable Resource Group scoped deployments for azd using the below command -
```
azd config set alpha.resourceGroupDeployments on
```

### Step 1a: Clone ARGUS repo and deploy resources

You need to clone ARGUS repo from github.  

Use the following command -  
```
git clone https://github.com/Azure-Samples/ARGUS.git
```

Now you need to enter into the directory of repo you just cloned.  
E.g., use the following command -  
```
cd ARGUS  
```  
> [!TIP] Update the WorkspaceResourceId in the main.bicep file in infra folder, with the resource ID of Log Analytics Workspace which you created earlier.  

Then deploy the resources using the following command - 
```
azd up  
```  

### Step 1b: (Alternative) Manual deployment

With the provided main.bicep file you can deploy resources manually.

Use the following command -
```
az deployment group create --resource-group <your-resource-group> --template-file main.bicep
```  

### Step 2: Run the Streamlit frontend
Change the directory to ```frontend``` folder.  

Install the dependencies with the following command -  
```pip install -r requirements.txt```  

Save .env.temp file as .env file -  
```mv .env.temp .env```  

Run Streamlit app with the following command -
```streamlit run app.py```



## Where to next?

**[🏠Home](../README.md)** - [ Quest 2 >](quest2.md)

[🔝](#)