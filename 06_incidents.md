<div align="center">
    <a href="./README.md">
        <img src="img/header.png"/>
    </a>
</div>

# 06 - Incidents and Investigations  


### Incidents
Given that we set our previous rule to look at logs over a 24 hour period, and that we earlier listed the keys in our storage account. We should have an incident raised. 

1. Click on 'Incidents' in the threat management section of the Sentinel Overview page. You should see 1 new incident that has been created based on the rule that we just created in the previous module. 
2. You can manage this incident in Azure Sentinel, you can assign it to a team member, adjust the severity, status, or add comments, These are done within the details pane on the right hand side. 
3. If you click on view full details, you can look at the incident in more detail, specifically in the left hand pane, if you click on any of the icons under 'Evidence' or 'Entities' this will spawn a KQL query to present you with the raw data. 

### Investigations
You may have noticed an 'Investigate (Now available) button. This is going to help up map our attacker and their potential movement through our network. This is where the entities come in handy. 

1. Click on the 'Investigate (Now available)' button.
2. Here you can see the alert, and the attached entities in a visual graph. 
3. Hover over any of the entities, IP address for example, you can then click 'related events' you will see the entities mapped to any relevant events. 
4. You can hover over the Alert and click 'Events' and it will again, take you to the raw data. 
5. If you click on the Timeline button in the top right, you will be able to see a periodic timeline of events within the map. 
 
Next, we're going to look at threat hunting.

----

[![Previous](img/previous.png)](./05_analytics.md) [![Next](img/next.png)](./07_hunting.md)