# How to quickly spin up an Azure Web Application

## A quick and simple way to run a static HTML website on Azure Web App Service using the Azure CLI

> <sub>To get started, you first need to have a Microsoft Azure account. If you don't have one, you can create a free account [here.](https://azure.microsoft.com/en-us/free/search/?&ef_id=_k_Cj0KCQiA4NWrBhD-ARIsAFCKwWv39zVXs4ww7bj_IGmTJngZol8ZX835NOuvRgv7ygSk_rEe9lnrcGcaAg2vEALw_wcB_k_&OCID=AIDcmm5edswduu_SEM__k_Cj0KCQiA4NWrBhD-ARIsAFCKwWv39zVXs4ww7bj_IGmTJngZol8ZX835NOuvRgv7ygSk_rEe9lnrcGcaAg2vEALw_wcB_k_&gad_source=1&gclid=Cj0KCQiA4NWrBhD-ARIsAFCKwWv39zVXs4ww7bj_IGmTJngZol8ZX835NOuvRgv7ygSk_rEe9lnrcGcaAg2vEALw_wcB)</sub>

We will be creating the Web Application using the Azure CLI, it runs BASH or PowerShell. For this example we will be using BASH.

Once you are logged into your account, click on the Cloud Shell icon:
<br>

![Alt text](<imgs/Screenshot 2023-12-10 at 9.52.16 AM.png>)

- <sup>If you have never used the Azure CLI before a message will popup saying to create storage. You will need to create the storage before using the CLI.</sup>

Using the Azure CLI is a lot like using a Linux terminal. If you are familiar with Linux commands you will be able to run them inside the 'BASH' Azure CLI.

You can clone a Git repository or use your own local files to add them to your Web App. For this example I will clone a repository.

---

Once you have your files cloned or uploaded, change directories into the directory that holds all of your application files.

From here we will run the "az weapp" command, which is an Azure command that lets you manage your Web Apps.

```bash
az webapp up --location [location] --name [name] --html
```

<sub>`--location` is for your selected Azure Region.</sub>

<sub>`--name` is for the name of your Web App.</sub>

<sub>We use `--html` because it's a static HTML website.</sub>

<br>

![Alt text](<imgs/Screenshot 2023-12-09 at 5.27.15 PM.png>)

This command will create a resource group (unless a resource group is specified), create an App Service Plan, and Deploy the Web App.

---

Once the previous step is complete you can check to see if your Web App is up and running by running the following command:

```bash
az webapp list --query "[].{hostName: defaultHostName, state: state}"
```

![Alt text](<imgs/Screenshot 2023-12-09 at 5.40.09 PM.png>)

Our Web App is now up and running!

### Final Thoughts

This is a very simple use case for a Web Application. We setup a static HTML website and verified it was up and running. Examples of Web Apps are LinkedIn, Evernote, and Gmail. So now that you know how to deploy and manage a Web App, go out and experiment for yourself!
