<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 07 - Threat Hunting  

Sometimes we are either responding to an incident from our analytics, or we are just proactively hunting through our data to see if there is anything suspicious that we can identify. This is where Hunting can be very useful. 

### Exploring Queries
1. Click on the 'Hunting' tab within the Azure Sentinel overview page. 
2. Here you can see tehre a re a large number of hunting queries at your disposal, I encourage you to look at some of these queries and try and understand what they're trying to find. 
3. You will see the charachteristics of some hunting queries are very similar to the Analytics rules we created earlier.
4.  One nice thing we can do, is go ahead and run all queries within our workspace to see if we get any matches. Go ahead and click 'Run All Queries' 
5.  Now filter the list of hunting queries based on number of results (4th column)
6.  You should see that two hunting queries returned results. Common Deployed Resources and Rare Audit Activity initiated by User. 
7.  Click into 'Rare Audit activity initiated by User' and then click 'View Results' 
8.  If you look at the output, you can see to the right the 'OperationName' which is the activity that identified from the query. 
9.  Take some time to explore this query, hunting queries can be quite complex. This is often why serious threat hunters would prefer to use something like Jupyter notebooks to perform their hunting (more on that later). for now, let's say we saw something intersting in these results, and we want to save it for later. Then we need bookmarks.....

### Hunting Bookmarks

Bookmarks enable is to save a particular log / output from our hunting queries and grab it again later when / if we need it. 

1. Select one of the outputs from the above hunting query by clicking the check box to the left. 
2. Click 'Add Bookmark' just above the results.
3. You will see that you can
   1. name your bookmark
   2. Map fields in the data to entities within Sentinel (so you can investigate and link data later)
   3. Add custom tags
   4. Add any further notes
4. Click Save.
5. If we head back to the hunting tab within Azure Sentinel, and click on the 'bookmarks' tab. you will see your bookmark is now there for you to reference when need be.
6. Click on the three dots to the right of the bookmark, and you can choose to create a new incident, or add this bookmark to an existing incident, depending on what kind of hunting you're doing. 

### Azure Notebooks for Hunting

Unfortunately we could run a whole workshop on threat hunting alone. Serious hunters will want to leverage the power of a full programming language, data science and visualisation tools, as well as KQL to step through their data when performing their investigations. In order to do this, most hunters will leverage Jupyter notebooks. 

Azure Notebooks is a hosted version of Jupyter notebooks, with a free tier, enabling you to host your notebooks in the cloud and run them using free compute resources. 

Azure Notebook integration is build directly into the Sentinel Overview page. 

1. Select Notebooks on the left hand side of the page
2. You will see 8 already created notebooks for performing various hunting queries and guided investigation. 
3. These notebooks leverage the `kql-magic` and `msticpy` python libraries from Microsoft to query Log Analytics and perform threat intelligence.
4. You can select the notebook, see what data types are required for it to run, and then launch the notebook. (You do not need to click this for this workshop)
5. This will launch Azure Notebooks service and create a notebook from this template. 
6. There is a very active threat hunting community for Azure Sentinel and there are a lot more hunting notebooks available on the Azure Sentinel [Github Community](https://github.com/Azure/Azure-Sentinel)


----

[![Previous](img/previous.png)](./06_incidents.md) [![Next](img/next.png)](./08_playbooks.md)