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
In a bash or any other CLI client, run the following command

**Deploy to Azure container Apps**
```
az containerapp up --resource-group fastapi-azure-demo-rg --name fastapi-azure-demo --ingress external --target-port 3200 --source .

```

## Demo

![Demo](app/asset/demo.gif)

I wrote an article on how to deploy this API with Google Cloud Run. [Check it out here](https://arnoldighiwiyisi.hashnode.dev/build-and-deploy-a-sentiment-analysis-api-with-fastapi-docker-and-google-cloud-run)