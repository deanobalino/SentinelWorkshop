<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 08 - Automation with Playbooks

Security Orchestration, Automation and Response (SOAR) is something a lot of security analysts strive for  but often don't achieve. The tight integration between Azure Sentinel and Azure Logic Apps makes this easier than ever. 

Wecan create automated playbooks to run in response to the analytics queries that we defined earlier in the workshop. Let's go ahead and do that. 

**NOTICE - This written tutorial has not yet been completed. Please follow along with your in class instructor from this point onwards**

1. Click on the 'Playbooks' button on the left hand side in the Azure Sentinel Overview page. 
2. Click 'Add Playbook' This will launch Azure Logic Apps. Logic Apps is a low code service for desiging automated workflows.
   1. Give your logic app a name, mine is called `sentinelrareactivity`
   2. Use the existing `sentinelworkshop` resource group that we created earlier
   3. Select a location. 
   4. Click Create
3. It may take a few seconds to create, when it does, select 'Blank Logic App' as we'll be bulding ours from scratch.
4. Once loaded, search for 'Sentinel' in the search box, then select Azure Sentinel. 
5. Then select 'When a response to an Azure Sentinel alert is triggered'
6. You may need to authenticate Logic Apps with your Microsoft Account first. 
7. Click 'New Step'

**NOTICE - This written tutorial has not yet been completed. Please follow along with your in class instructor from this point onwards**

----

[![Previous](img/previous.png)](./07_hunting.md) [![Next](img/next.png)](./09_patterns.md)