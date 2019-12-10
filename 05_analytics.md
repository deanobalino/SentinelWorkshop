<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 05 - Analytics and Alerts  

We don't always want to proactively look at a workbook to know if something anomolous is happening. We need to have some periodic analytics configured on our data which will raise incidents for us when they detect anomolous activity. 

### Exploring Rule Templates
1. Within the Azure Sentinel Overview, select the 'Analytics' button on the left hand side, and then select the 'Rule Templates' tab. 
2. You will see a large number of rules listed by severity. Take some time to explore and look at these rules. Each one has some typical charachteristics. 
   1. A Name
   2. A Type - Scheduled / Microsoft Security / Fusion
   3. Required Data Sources
   4. Tactics - Mapped to the Mitre Attack framework
   5. Rule Query - The actual KQL query that, if returned, will raise an incident
3. Take your time to eplore these rules to understand the familiarity with them. You can even copy the rule query into the 'Logs' section within Azure Sentinel and see if it picks up anything. 

### Configuring our rule.
For the purpose of this workshop we're going to enable a single analytics rule to look for Rare subscription-level operations in Azure. 

1. Within the rule templates, search for 'rare subscription' to filter the list. You should see a rule called 'Rare subscription-level operations in Azure' Click on that rule template. 
2. Within the right hand pane click 'Create rule' 
3. You can see here that although Sentinel provided us this template, we are able to customise this to meet our specfic needs.
4. Leave the defaults on the first page, ensure the status is Enabled and click 'Next: Set rule logic' 
5. Here we can also customise a few important things
   1. The query itself (notice it's looking for people listing storage account keys)
   2. Mapping Entities, we can leave this for now but these will be used for incident investigation.
   3. How often to run the query, we can leave the defaults
   4. Alert Threshold, we want to keep this at zero. 
6. Click 'Next: Automated response' 
7. We will be looking at automated response later, so let's just click 'Next: review'
8. Then click 'Create' 

Next, we're going to look at if this rule has created any incidents and how we could investigate those. 

----

[![Previous](img/previous.png)](./04_workbooks.md) [![Next](img/next.png)](./06_incidents.md)