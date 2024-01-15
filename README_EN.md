## Escolha o idioma / Choose the language
- [Português (BR)](README_PT.md)
- [English](README_EN.md)


## Implementation of CI/CD Pipeline (Continuous Integration/Continuous Delivery)
<p align="justify"> CI/CD is a comprehensive term that covers various phases of DevOps. CI (Continuous Integration) is the practice of integrating code changes into a repository multiple times a day. CD has two meanings: Continuous Delivery automates code integrations,
while Continuous Deployment automatically releases final builds to end users. Frequent CI/CD testing reduces errors and code defects, making them essential for any workflow.</p>

## Document Contents
  * Authors
  * Overview
  * Prerequisites
  * Configuration
  * Usage
  * License

## Autors:
Vinícius Peters<br>

## Overview
<p align="justify">The implementation of the CI/CD pipeline is necessary to streamline and standardize the structure of your environment, ensuring the quality of code from the development environment to its implementation in the production environment, which is done automatically after the approval of artifacts. This document contains the procedure to implement this CI/CD structure using Github Actions and the Azure environment.</p>


## Prerequisites:
  * Have a service user with access permission to Synapse.
  * GitHub account with a created repository.
  * READER permission on the resource group.
  * CONTRIBUTOR permission on Synapse-Production.
  * Grant permission from the Service Principal.
  * Have a Development (DEV) and Production (PROD) Synapse environment.

    
## Configuration
### File readme.yml

<p align="justify"> In your Github repository in the code tab, click on <strong>creating a new file<strong>.</p>
<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/1.%20Creating%20New%20File.png">
</kbd>
<br><br><br>
<p align="justify"> In the file path, create a file called "readme.yml" in the following folder structure ".github/workflows/readme.yml". Once this is done, click on <strong>Commit Changes...<strong></p> 

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/2.Readme.yml.png">
</kbd>
<br><br><br>

### Link Synapse to Github
<p align="justify">Open Synapse DEV,  and from the icons on the left select <strong>Manage</strong> and then, select the last option <strong>Git configuration</strong>. Then, select the <strong>Configure</strong> button in the middle of the screen.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/3.%20Git%20Configuration.png">
</kbd>
<br><br><br>
<p align="justify">In <strong>Repository Type</strong>, select GitHub and in <strong>Github repository owner</strong>, enter the account owner's name.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/4.%20Configurar%20Reposit%C3%B3rio%20github%201.png">
</kbd>
<br><br><br>
<p align="justify"> In <strong>Repository name</strong>, select the desired repository. For the other fields do not change any configurations and click <strong>Apply</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/5.%20Configurar%20Reposit%C3%B3rio%20github%202.png">
</kbd>
<br><br><br>

### Create a New Branch
<p align="justify">On the top left corner,click on<strong>New Branch[Alt+N]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/6.%20Criando%20Nova%20Branch.png">
</kbd>
<br><br><br>

<p align="justify">Enter a name for your branch  create it based on main branch as shown in the example below. Then, click on <strong>Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/7.%20Criando%20Nova%20Branch%202.png">
</kbd>
<br><br><br>

### Workspace_publish
<p align="justify">The workspace_publish branch will be created automatically after being done a publish in Synapse DEV. To do that, make a publish to the same branch you created. Create a pipeline with a <strong>Set variable</strong> activity and create a variable. Once created, click on<strong>Commit all</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/8.%20Vari%C3%A1vel%20para%20Publica%C3%A7%C3%A3o.png">
</kbd>
<br><br><br>

Click on <strong>OK</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/9.%20Confirmando%20Publica%C3%A7%C3%A3o.png">
</kbd>
<br><br><br>
<p align="justify">Once that is done, you will need to create a <strong>Pull Request</strong>. To do that, click on the name of your created branch in the top left corner and look for <strong>Create pull request[Alt+P]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/10.%20Criar%20Solicita%C3%A7%C3%A3o%20de%20Pull.png">
</kbd>
<br><br><br>
<strong>OBS:In the following steps, you can only approve a pull request if you're the approver. Otherwise, make a request to the approver.</strong>
<br><br>

<p align="justify">Open your Github repository, click on <strong>Create pull request</strong> or <strong>Compare & pull request</strong>  as shown in the image below.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/11.%20Criar%20Solicita%C3%A7%C3%A3o%20de%20Pull%202.png">
</kbd>
<br><br><br>

<p align="justify">An "Open a pull request" tab will open. Click on <strong>Create pull request</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/12.%20Cria%20Solicita%C3%A7%C3%A3o%20de%20Pull%203.png">
</kbd>
<br><br><br>

<strong>Merge pull request</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/13.%20Merge%20Pull%20Request.png">
</kbd>
<br><br><br>

<strong>Confirm merge</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/14.%20Confirmar%20Merge.png">
</kbd>
<br><br><br>

After completing the previous steps, now open your <strong>main branch</strong> and click on <strong>Publish</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/15.%20Publicar%20Main.png">
</kbd>
<br><br><br>

### Finding syn-deploy-yml file

<p align="justify"> The contents of <strong>syn-deploy.yml</strong> file will be used for the activities below.</p>
<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/16.%20Caminho%20de%20Pasta%20do%20Arquivo%20syn-deploy.yml.png">
</kbd>
<br><br>

### Github Repository Settings

<p align="justify">Inside your GitHub repository, select the <strong>Code</strong> tab and search for <strong>workspace_publish</strong>. Create a folder structure following this pattern: <strong>.github/workflows/syn-deploy.yml</strong></p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/17.%20Arquivo%20syn-deploy.yml.png">
</kbd>
<br><br><br>
<p align="justify"> And at the end, place the file with the environment parameters, look for the <strong>syn-deploy.yml</strong>strong> file in the folders on the side, copy all the code and paste it into the file you just created, following the path shown in the image above.</p>


### Configuring syn-deploy.yml File
<p align="justify">Inside the <strong>syn-deploy.yml</strong> file, adjust the three lines <strong>TemplateFile,ParametersFile e OverrideArmParameters</strong> with the name of your workspace, as shown in the image below, highlighted in red. Note that the file contains lines that will be values inherited from Github Secrets (consider the ones with "${{secrets.____}}). These secrets will need to be assigned in Github</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/17.%20Arquivo%20syn-deploy.yml.png">
</kbd>
<br><br><br>
These will be the parameters that will be inherited from Github:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

### Configuring Secrets Github

Go to <strong>Settings</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/19.%20Settings.png">
</kbd>
<br><br><br>
<p align="justify">On the left side of the screen, go to <strong>Secrets and variables</strong> and <strong>Actions</strong>. In the <strong>Secrets</strong> tab, select <strong>New repository secret</strong>.In this repository, you will assign the value of the variables that will be inherited in the <strong>syn-deploy.yml</strong> file.</p>


<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/20.%20Secrets%20Github.png">
</kbd>
<br><br><br>
<strong>It is worth mentioning that all these parameters must be filled in with the data from the Production environment.</strong>

Assign the name of the secret and the value. In this case, it will be assigned to each of these:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

Example:<br>
<strong>Name</strong> = WORKSPACENAME<br>
<strong>Secret</strong> = your workspace name<br>

Then, click on <strong>Add secret</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/21.%20Adicionando%20Secret%20no%20Github.png">
</kbd>
<br><br><br>

### How to Find Each of the Parameters

To find the parameters:<br>
* <strong>WORKSPACENAME</strong><br>
* <strong>RESOURCEGROUP</strong><br>
* <strong>SUBSCRIPTIONID</strong><br>

<p align="justify">In Azure Portal, search for your production Synapse workspace. On the left tab, go to <strong>Overview</strong> and you will find the information for the three parameters listed above.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/22.%20Parametros%20Workspace.png">
</kbd>
<br><br><br>

To find the parameters:<br>
<strong>CLIENTID</strong><br>
<strong>CLIENTSECRET</strong><br>
<strong>TENANTID</strong><br>

<p align="justify">A service principal should be created.In the search bar, type <strong>App Registrations</strong> and click on it.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/23.%20App%20Registrations.png">
</kbd>
<br><br><br>
After that, click on <strong>+New registration</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/24.%20Novo%20Registro%20App%20Registrations.png">
</kbd>
<br><br><br>
After that, assign any name and press <strong>Register</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/25.%20Registrar%20Application.png">
</kbd>
<br><br><br>

<p align="justify">Once created, you will be taken to the <strong>Overview</strong> page of the service principal. Here, you will find the <strong>CLIENTID</strong> and <strong>TENANTID</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/26.%20Clientid%20e%20Tenantid.png">
</kbd>
<br><br><br>
<p align="justify">For the <strong>CLIENTSECRET</strong>, in the left side option bar, you will find the option <strong>Certificates & secrets</strong>. After clicking on this option, click on <strong>+ New client secret</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/27.%20ClientSecret%20.png">
</kbd>
<br><br><br>
<p align="justify">In <strong>Description</strong> Put a description of your preference. Then, click on <strong> Add </strong>.</p>


<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/28.%20ClientSecret%202.png">
</kbd>
<br><br><br>
<p align="justify">Once created, it will appear in the <strong>Value</strong> column the <strong>CLIENTSECRET</strong> value. Record this value, it will <strong>only appear once and you will not be able to see it again!</strong></p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/30.%20Value%20Secret.png">
</kbd>
<br><br><br>

### Assigning Permissions to the Service Principal

<p align="justify">With all the parameters filled in from the previous steps, sign in to your <strong>Production</strong> Synapse workspace and go to <strong>the Access Control (IAM)</strong> options and click on <strong> Role assignment</strong>.Look further up for the <strong>+ Add</strong> option. </p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/31.%20Add%20permiss%C3%A3o.png">
</kbd>
<br><br><br>
<p align="justify">The Primary Service <strong>Reader permission</strong> will be assigned to the production resource group. To do this, select the first option of Reader and then <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/32.%20Add%20Permissao%202.png">
</kbd>
<br><br><br>
<p align="justify">In Members tab, click on the <strong>+ Select members</strong> option. Use the search bar next to it to choose the user and click <strong>Select</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/33.%20Add%20Permissao%203.png">
</kbd>
<br><br><br>
After that, click on <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/34.%20Add%20Permissao%204.png">
</kbd>
<br><br><br>
<p align="justify">Given the Reader permission, repeat the previous step, but now give the <strong>Contributor</strong> permission to the production workspace. Click <strong>Role Assigment</strong> and then <strong>click +Add</strong>.Select the Privileged Administrator roles tab, and click <strong>Contributor</strong>. Then click <strong>Next</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/35.%20Permissao%20Contributor.png">
</kbd>
<br><br><br>
<p align="justify"> Members tab, click <strong>+Select members</strong> and select the user to apply the <strong>Contributor</strong> permission to.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/36.%20Permissao%20Contributor%202.png">
</kbd>
<br><br><br>

Click <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/37.%20%20Permissao%20Contributor%203.png">
</kbd>
<br><br><br>

Finally, open Production Synapse Studio.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/38.%20Open%20Synapse%20Studio.png">
</kbd>
<br><br><br>
<p align="justify">Go to the <strong>Manage</strong> option on the left side and <strong>Access control</strong>. Click <strong>+ Add</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/39.%20Permissao%20Synapse%20Artifact.png">
</kbd>
<br><br><br>
<p align="justify"Select the <strong>Synapse Artifact Publisher</strong> role. On the bottom bar, you must select the Service Principal user you previously created and click <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/40.%20Permissao%20Synapse%20Artifact%202.png">
</kbd>
<br><br><br>

### Configure Azure Key Vault

<strong>A Key Vault should be created for each Synapse DEV and PROD environment.</strong>

In portal Azure, go to the search bar and type <strong>Key Vaults</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/41.%20Key%20vaults.png">
</kbd>
<br><br><br>
Click <strong>+Create</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/42.%20Create%20Key%20Vault.png">
</kbd>
<br><br><br>
<p align="justify">After that, fill in the key vault creation information by assigning the resource group that was created in the Synapse Development. Then, go to <strong>Review+Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/43.%20Create%20Key%20Vault%202.png">
</kbd>
<br><br><br>
<p align="justify">In production Key Vault, click on the left side <strong>Access Control(IAM),</strong> click <strong>+Add</strong> and then click <strong>Add role assignment</strong>.</p>


<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/44.%20Access%20Control%20Key%20Vault.png">
</kbd>
<br><br><br>
In <strong>Role Assignments,</strong> look for <strong>Key Vault Secrets Officer</strong>. Then click <strong>Next</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/45.%20Key%20Vault%20Secrets%20Officer.png">
</kbd>
<br><br><br>
<p align="justify">After that, go to Members and in the <strong>Assign access to</strong> option, select <strong>Managed identity</strong>. Once selected, click on <strong>+Select Members</strong>.</p>

In <strong>Managed Identity</strong> select Synapse workspace(). After that, select your Production Synapse environment.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/46.%20Key%20Vault%20.png">
</kbd>
<br><br><br>

### Configure Linked Service

In your DEV Workspace, go to <strong>Manage<strong> and <strong>Linked services</strong>. Click <strong>+ New</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/47.%20Linked%20Service.png">
</kbd>
<br><br><br>
In the search bar, search for <strong>Azure Key Vault</strong> and click <strong>Continue</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/48.%20Linked%20Service%202.png">
</kbd>
<br><br><br>
<strong>Name:</strong>  Give Key Vault a name.<br>
<strong>Azure Subscription:</strong> Select your subscription.<br>
<strong>Azure Key Vault name:</strong> Select the Key Vault created from the production environment.<br>

For the others, leave it default. After that, press <strong>Commit</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/49.%20Linked%20Service%203.png">
</kbd>
<br><br><br>
<p align="justify"> The next step you will need to publish something again in DEV with the Linked Service properly created (repeat the step in topic Workspace_publish).</p>


<p align="justify">After that, you will have to enter your <strong>TemplateWorkspace.json</strong> file and search for the KV name that was automatically generated as shown below:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/50.%20TemplateforWorkspace.png">
</kbd>
<br><br><br>
<p align="justify">  Copy the "LS_KV_DEV_properties_typeProperties_baseUrl" and <strong>the defaultValue</strong>. They will be used in the next step for creating the <strong>ParameterPRD.json file</strong>.

### Creating ParameterPRD.json file

<p align="justify"> In your Github repository, create a file named <strong>ParameterPRD.json</strong> inside your DEV workspace folder and paste the previously copied parameters into the following format:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/51.%20ParameterPRD.png">
</kbd>
<br><br><br>
<p align="justify"> For the name of the <strong>ParameterPRD.json</strong> file, make sure that the is exactly the same as the name that is in the <strong>syn-deploy.yml</strong> file in <strong>OverrideArmParameters</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/52.%20OverridearmParameters.png">
</kbd>
<br><br><br>

## Usage

<p align="justify"> In your Development environment branch after making changes, the process to take them to <strong>production</strong> will follow these steps:</p>

<p align="justify"><strong>Commit</strong> your changes. In the example below, we will use "Pipeline 2" in the product branch:

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/53.%20Teste%20Pipeline%202.png">
</kbd>
<br><br><br>
<p align="justify"> Create a <strong>Pull request</strong> to the main branch.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/54.%20Pull%20Request%20Pipeline%20Teste.png">
</kbd>
<br><br><br>
<p align="justify"> After your<strong>Pull request is approved</strong>, the main branch will have all your changes. Therefore, the person responsible for the Pull Request should click on Publish as shown in the image below:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/55.%20MainBranch%20Publish%20Teste.png">
</kbd>
<br><br><br>
<p align="justify"> Wait until the success message appears on your screen:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/56.%20Generating%20templates.png">
</kbd>
<br><br><br>
<p align="justify"> After that, go to the <strong>production</strong> environment and you will see your changes in the production environment:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/57.%20Altera%C3%A7%C3%B5es%20em%20Prod.png">
</kbd>
<br><br><br>
CI/CD finished!
