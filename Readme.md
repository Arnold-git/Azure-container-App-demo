# Sentiment Analysis API :rocket:

The purpose of this README.md file is to explain the steps required to setup this project in your local environment for testing.

### How do I get set up? :pushpin:

### Requirements 
* Python
* Docker
* Azure acount
* Azure CLI

## Setting up with Python ### 

**Clone Repo**
```
git clone https://github.com/Arnold-git/Azure-container-App-demo
```

**Change current working directory**
```
cd Azure-container-App-demo
```

**Create a Virtual environment**
```
python -m venv .venv
```
**Activate virutual Environment**
```
#windows
source .venv/Scripts/activate
#linux
source .venv/bin/activate
```

**Install dependencies**
```
pip install -r app/requirements.txt
```

**Start Server**

```
uvicorn app.main:app --reload
```
## Setting up with Docker ### 
**Build and Run container image**
```
docker build --tag fastapi-azure-demo . && docker run -d --name fastapi-azure-container -p 3200:3200 fastapi-azure-demo
```

Open the ![](http://localhost:3200) URL in your browser to see the web app running locally.

## Deploy to Azure Container App ### 
In a bash or any other CLI client, run the following command in the project root folder

**Deploy to Azure container Apps**

```
az containerapp up --resource-group fastapi-azure-demo-rg --name fastapi-azure-demo --ingress external --target-port 3200 --source .

```
You should see this in your terminal when the deployment is complete.
![](app/asset/azure-cli-01.png)

**Monitor logs**
```
az containerapp logs show --name fastapi-azure-demo --resource-group fastapi-azure-demo-rg --type console --follow

```
![](app/asset/azure-cli-02.png)

**clean up**
```
az group delete --name fastapi-azure-demo-rg

```

## Demo

![Demo](app/asset/demo.gif)

I wrote a detailed article [Check it out here](https://arnoldighiwiyisi.hashnode.dev/how-to-deploy-fastapi-web-application-on-azure-container-apps)