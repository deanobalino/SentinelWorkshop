<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 04 - Data Connectors and Workbooks  

In this section we will be exploring our data connectors a little more to see what they provide out of the box.  


### Exploring Workbooks

1. Navigate to the Azure Sentinel Overview in the Azure portal. 
2. Select the "Data Connectors" button on the left under Configuration
3. Explore the list of Data Connectors to see what is available
4. Select the 'Azure Activity' connector
5. Select 'Open connector page'
6. Note that Under 'Related Content' there are 2 queries and 1 workbook. Let's look at these. Click on either.
7. Note we have some sample queries here. These should look familiar now that we know a little about KQL. 
8. Click on the Azure Activity Under 'recommended workbooks'
9. Select the workbook and click 'Save', choose any region. 
10. Select 'View saved workbook'
11. We can see that out of the box, you have a dashboard to demonstrate Azure Activity. Without having to configure anything. You can also edit these workbooks to make them suit your needs. You can always go straight to the workbooks tab from the Sentinel overview pane to browse the gallery of workbooks. Let's do that. 
12. Back in the overview, you should now be able to see your 'saved workbooks' and 'Templates' you'll see in templates that there are a large number of workbooks available for each connector. But let' go ahead and build our own custom workbook. 

### Creating a Custom Workbook

You may wish to aggregate data from different connectors, or just have some custom logic that meets your specific requirements. To do that, you'll need to create a custom workbook. Here's how. 

1. Within the workbook overview, click 'Add Workbook' at the top. 
2. This will give us a simple new workbook that shows us all of our log tables and how many logs we have from each. 
3. Go ahead and click 'Edit' to start making this your own. 
4. Now, you can edit each section in the Workbook. If you click the 'Edit' button below any section you will see the raw data/query. Some is Markdown, some is KQL. Let's add some of our own data. 
5. Select 'Add Query' and copy the below query in. 
   ```
    AzureActivity
	| summarize count() by CallerIpAddress
    | render barchart
   ```
6. Click 'Run Query' Now you'll see that data represented as a bar chart. Notice you can also set parameters like timeframe etc within this cell. Click 'Done Editing' (the one below your bar chart. 
7. Let's now add some Markdown to add a title. click 'Add Text'. Within this cell, we'll put:
   ```
   # Requests per source IP Address
   ```
8. Looking good, but we need to put it above the chart, click the small up arrow beneath the cell to move the cell up within the workbook. Then click 'Done Editing'.
9. Now it's looking nice and smart. Here's a couple of more queries you could try out and add to your workbook to get better insight. Feel free to be creative, using your KQL knowledge from the previous module. 

**List how many logs there has been today, setting timeframe in query**
```
let StartTime=ago(24h);
let StopTime=now();

AzureActivity
| where TimeGenerated > StartTime and TimeGenerated <= StopTime 
| count
```

**Show the latest 10 logs and project only the data we wish to see.**
```
AzureActivity 
| top 10 by TimeGenerated
| project TimeGenerated, OperationName, ActivityStatus, Resource, Caller, CallerIpAddress, ResourceGroup
```  
  
Next, we'll be looking Analytics and Alerts.  

----

[![Previous](img/previous.png)](./03_kql.md) [![Next](img/next.png)](./05_analytics.md)