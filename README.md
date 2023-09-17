# wo-skill-dev-documentation
## Overview
This repo contains the details of the skill building guidelines. Revisit this documentation for updates to the skill guidelines before starting any new skill development.

## Getting Started 
Understanding [ Concepts ](https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/462726b4-9778-46af-a58e-244d24ae2b42)

### Skill Flows:
Skills are often more valuable when combined with other skills. You can create a linear sequence of skills by using a skill flow. Structure your skill flow to use two or more skills to complete a task. These skills can be from different applications. Using a skill flow, you can combine multiple functional calls to carry out a single workflow.
Below is a blueprint of steps involved in building skills in WO.

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/1b4f44b2-bc3c-4885-90df-e3313d55d047"> 

Start with analysing the end to end usecase in mind and start building the skills and skill flows needed to achieve the same.

You might want to update yourself with the Best practices for skill designing from here [ UX guidelines ](https://www.figma.com/proto/ADaIAp27ywuc3obTpSn3zW/Skill-guideline-for-WO?page-id=1%3A3&type=design&node-id=701-24516&viewport=480%2C327%2C0.03&t=KQzqoDVDOW1ozjV1-1&scaling=scale-down&starting-point-node-id=701%3A23586&mode=design)



With this background in mind, it's time to get into the actual process of creating your skill.
Before you begin check whether skill has been already developed . You can check list of existing supported applications for [watsonx Orchestrate here]( https://www.ibm.com/docs/en/watson-orchestrate?topic=built-in-apps).

If you do not have ready OpenAPI and want to build one from scratch skip to this [section](Building OpenAPI from scratch). 
. 

## Skill Development:

Creating skills from [OpenAPI files](https://www.ibm.com/docs/en/watson-orchestrate?topic=files-creating-skills-from-openapi)

Enhance the openAPI file into an exemplary watsonx Orchestrate [skill](https://www.ibm.com/docs/en/watson-orchestrate?topic=skills-enhancing-publishing)

After a skill is enhanced and published, it is available for you to add to your skill set from the skill catalog. For instructions, see [Adding a skill from skill catalog](https://www.ibm.com/docs/en/SSAVQO/skills/skill_addremove.html#adding-a-skill-from-skill-catalog)


Tip:Users with the Admin/ Builder role can add the skill to a team skill set.

Now that you have the required skills available, time to move on to build the end-to-end usecase as a skill flow. 

### Combining skills into skill flows
Combine the skills into a time-saving [skill flow](https://www.ibm.com/docs/en/watson-orchestrate?topic=combining-skills-into-skill-flows )

### Skills testing: 
Test the skills by invoking them via the tiles on home page or via utterances and ensure your skills are working as expected. Tweak the skills to adhere to the [UX guidelines](https://www.figma.com/proto/ADaIAp27ywuc3obTpSn3zW/Skill-guideline-for-WO?page-id=1%3A3&type=design&node-id=701-24516&viewport=480%2C327%2C0.03&t=KQzqoDVDOW1ozjV1-1&scaling=scale-down&starting-point-node-id=701%3A23586&mode=design)

After sufficient testing [export the skills](https://www.ibm.com/docs/en/watson-orchestrate?topic=skills-exporting)

### Push the skills into Github repository in this structure 

Merge the skills (.json files) into your Github repo here. Add a documentation guide for the users of this skill to use the skills efficiently.

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/69e45726-3738-49cd-a9d3-692d64dbbdf7">

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/2f1be293-d3e6-434e-af8f-fd8adf90b09b">


### Approval
Add your test evidences like screenshot of the test 

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/5be773ac-07e7-4a98-a8a1-dcfe22e29f65">


### Publishing the skill to be part of Watson Orchestrate Global skills catalog:
Indicate in the README.md if you want your skills to be published by IBM Watsonx Orchestrate team to be part of the out of the box global skills catalog.Once they are part of the global catalog in subsequent release, you can test the skills on your production instance of Watsonx orchestrate.



## Building OpenAPI from scratch:

You can build an OpenAPI using a text editor or use an IBM tool called CDK to build from a CURL command. Login to CDK tool here - https://explorer.automation.ibm.com/cdk 

1.	Identify the API developer documentation for the identified set of skills / APIs.
Eg: https://developer.webex.com/docs/api/v1/recordings , narrow down to the exact api - https://developer.webex.com/docs/api/v1/recordings/list-recordings

2.	Login to Connector Development Toolkit using IBM ID (https://explorer.automation.ibm.com/cdk) . You can link any email id as IBM ID, for partners onboarded as IBM sub-contractors it advisable to use IBM w3 id as the IBM id. 

3.	Click on Create a Connector and provide the essential details like Application name, Icon, Attach OpenAPI spec file if available. 

<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/667ef505-79bb-46b8-a48b-a9c9b8f7a16e">

 


4.	If OpenAPI is not available proceed with clicking on Create Connector and then proceed to next steps where it allows you to create OpenAPI from scratch.

Create a Group(optional) to group a set of APIs together.
Example: WebexRecording group 

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/f6055ad0-f967-42e9-8926-bcb3bf273c21">



5.	Create Actions for WebexRecording API using CURL command
Most API documentation provide curl commands for the APIs like this example from Workday, 
 
 
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/79cbdeb4-5b6a-4e83-930c-c351f557bbf6">


If a CURL command is not readily available we can get one by trying in PostMan

 
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/35fced6b-7d4d-4f00-8dfa-36d4022d5dd0">



Request:

https://webexapis.com/v1/recordings?from=2020-07-12T09:30:00+08:00&to=2020-07-31T09:30:00+08:00&meetingId=f91b6edce9864428af084977b7c68291_I_166641849979635652&hostEmail=john.andersen@example.com&siteUrl=example.webex.com&integrationTag=dbaeceebea5c4a63ac9d5ef1edfe36b9&topic=John's%20Meeting&format=ARF&serviceType=MeetingCenter&status=%5Bobject%20Object%5D,%5Bobject%20Object%5D

  <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/d292cb06-14e4-46c8-9062-5edb38de6593">


 

In PostMan, on right hand corner click on the code button -  

 




6.	Copy the curl command into the CDK and click on Add action

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/c6d1d762-f2f9-4310-933b-faf3aab1e193">


7.	ListRecording API is created now

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/b32c2521-8f75-4dc1-ab44-41b255b4ce97">



8.	Use the Request and Response tabs to change any of the fields, mark any of them as mandatory, add new fields, Pagination etc.
   <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/75854a24-ffaf-4700-ad2f-98457f817de3">

 

9.	Create the response schema by copying the response example from Webex developer docs
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/5ef42b83-8c64-4e8d-b55a-db875793037d">

 


10.	Add or remove any of the response fields needed / not needed
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/c22c70ce-01e6-4c7f-b6a4-aa80cc69138f">

 


11.	Use the Connection Properties tab to add the requirement Authentication scheme for the API
Example: Webex takes Bearer Token
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/764be1d7-1592-4919-bc5c-d5c5cd1cd6bc">

 

13.	Test the API by providing the connection credentials
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/32d305a4-ec7f-48c7-a554-4567c885bb2d">

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/9d4d0076-767d-487a-a796-e8535dd77e51">



14.	After successfully connecting, test the APIs

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/be22d15f-b428-49d0-99d8-ca4a0fb73e57">




15.	Download the connector

 


16.	Decrypt the .car file to extract the raw OpenAPI needed for WO Skill, using the command provided by IBM.

Now you can continue the skill development.


