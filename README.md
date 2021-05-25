# Getting Started React App with GitHub Actions

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

You can create and deploy React.js application on Azure Web Apps.

## How to use

### Clone this Repository

Choose clone or fork this repository

#### Clone

```sh
git clone <url of this repo>
cd react-web-app-deploy
rm -rf .git
```

### Create Web App BEFORE you deploy

```sh
LOCATION=japaneast
WEBAPP_NAME=
ASP_NAME=
RESOURCE_GROUP_NAME=

az group create --name $RESOURCE_GROUP_NAME  --location $LOCATION
az appservice plan create --name $ASP_NAME --resource-group $RESOURCE_GROUP_NAME --sku P1V2
az webapp create --name $WEBAPP_NAME --resource-group $RESOURCE_GROUP --plan $ASP_NAME
```

### Set PublishSettings as secret

Download PublishSetting file from Azure Portal.

Create new secret `AZURE_WEBAPP_PUBLISH_PROFILE` and paste your PublishSetting.

![secret](./images/secrets.png)
