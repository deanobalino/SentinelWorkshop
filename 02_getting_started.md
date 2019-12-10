<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 02 - Getting Started  

First things first, we need to log into our Azure accounts and configure Azure Sentinel. 

### Applying your Azure Pass
If you require an Azure Pass please follow the below, otherwise you may skip this step. 

1. Head over to https://www.microsoftazurepass.com/Home/HowTo for instructions on how to redeem your Azure Pass.
2. Ask the workshop presenter for your pass code. 

### Creating an Azure Sentinel workspace
1. Within the azure portal (https://portal.azure.com) type 'sentinel' in the top search bar and select 'Azure Sentinel' 
2. Click ' Add' in the top left to create a Sentinel Workspace. You'll be prompted to create a new workspace.
   1. Give your workspace a globally unique name
   2. Select your subscription
   3. Create a new resource group, call this 'sentinelworkshop' 
   4. Select a preffered region. (West Europe will be used in the in person workshop in London)
3. Click OK, and wait for the workspace to be created. this may take a few seconds. 
4. Once created, you will see the UI adapt and you can then select the workspace you just created and click 'Add Azure Sentinel' 
5. That's it, you now have an Azure Sentinel Workspace! 

### Adding some data sources
There's no point having a SIEM without having any data for it to analyse, so let's quickly give it some data. 

1. Click on 'data connectors' on the left hand size of the Azure Sentinel overview within the portal. 
2. Select 'Azure Active Directory' then select 'Open Connector page'. 
3. You will see some validation checks are being ran. once complete you should be able to click 'connect' for the Azure Active Directory Sign In and Audit Logs. Go ahead and click connect for the Audit Log. 
4. Now we've configured Active Directory logs, let's add the Azure Activity log. Head back to 'Data Connectors' and locatte the 'Azure Activity' connector.
5. Open the connector page again and click 'Configure Azure Activity Logs' 
6. Select your subscription within the table, and then simply hit 'connect'

As you can see, many other data connectors are available, but for the purpose of this workshop, we won't be configuring those.

### Generating some interesting traffic
It will look for now as if our connections were not sucessful. This is because they will not show as connected in the Sentinel Overview until we start sending some traffic. So let's make some stuff happen. 

**Creating a user**
1. Navigate to Azure Active Directory (AD) in the Azure Portal by simply searching within the search bar at the top. 
2. When in Azure AD, select 'Users' on the top left.
3. Select 'New User' at the top of the page. 
4. Create a dummy user for your account. Remember the username you selected.
   1. Do not select any groups or roles
   2. Select 'Auto-generate password' and then copy the password to your clipboard or a text file for later reference.
   3. You may leave any non required fields blank
5. Open a new incognito/private window and navigate to the Azure portal. Login as your new user. (you will need the full username including the .onmicrosoft.com part)
6. Back in your own browser, reset the password of the new user. Copy the temporary password to your clipboard.
7. Log out in the private window as your new user, and log back in with their temporary password. you will be prompted to create a new one. Do so and then login. **NOTE: password will need to have numbers, capitals, special characters for it to be accepted.**
8. That should have generated us some Azure AD Audit logs. 

**Creating Cloud Resource/s**
1. In the Azure portal (back now as yourself) navigate to 'Storage Accounts' service by typing it in the search box at the top of the page and clicking it.
2. Click 'Add' to create a new storage account. 
   1. Select your existing resource group `sentinelworkshop`
   2. Give it a globally unique name
   3. Select any location you wish
   4. Leave the rest as default
   5. Click Review + Create
   6. Click Create
3. Within our storage account, on the left hand side, click the 'Access Keys' button, this will show us the secrets for accessing our storage account. This should make some interesting logs. 
4. We now have some Azure Activity that we should be able to see in our logs too.
----

[![Previous](img/previous.png)](./01_intro.md) [![Next](img/next.png)](./03_kql.md)
