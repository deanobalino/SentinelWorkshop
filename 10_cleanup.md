<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 10 - Wrap Up / Clean Up

Thank you for completing the Cloud Native SecOps with Azure Sentinel Workshop. 

So that you don't get charged for any tailing resources, we've been delpoying everything into a single resource group called `sentinelworkshop`. So to clean things up, we can simply:

1. Type 'Resource Groups' in the search bar at the top of the Azure Portal and select 'Resource Groups'
2. Click on the `sentinelworkshop` Resource Group
3. Click 'Delete Resource Group' at the top of the page. This will delete the resource group and all of it's contents. 
4. you will be prompted to type the name of the Resource Group to confirm deletion. 
5. First, ensure you're OK with deleting everything in this resource group. If so, Type the name and click 'Delete'.

We also created a user in Azure AD. 

1. Head back over to Azure AD in the portal by searching for 'Azure Active Directory' in the search bar and selecting the service.
2. Click on 'Users' on the left hand side.
3. Click on the name of the User you wish to delete.
4. Click 'Delete' at the top of the pane. 
5. You will be asked to confirm. If confident, then confirm and the user will be deleted. 

Everything that we created in this workshop should now be deleted and you will not incur any further costs for these resources. If you want to double check this, you can always navigate to the 'All resources' section of the Azure Portal by searching in the top search box and making sure there aren't any stray resources left behind.

----

[![Previous](img/previous.png)](./09_patterns.md) 