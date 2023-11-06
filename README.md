# wo-skill-dev-documentation
## Overview
Learn how to build skills for use in IBM watsonx Orchestrate. Every time you start to develop new skills, revisit this information for updates. 

For style guidelines, such as information about naming and describing skills and examples of the help text to provide, refer to the [Skill design content guidelines](https://www.ibm.com/docs/en/watson-orchestrate?topic=files-skill-design-content-guidelines).

## Getting started 
To get started, understand the concepts by reading [Apps and skills](https://www.ibm.com/docs/en/watson-orchestrate?topic=apps-skills).

### Skill flows
Skills are often more valuable when combined with other skills. You can create a linear sequence of skills by using a skill flow. Structure your skill flow to use two or more skills to complete a task. These skills can be from different applications. Using a skill flow, you can combine multiple functional calls to carry out a single workflow.

The following blueprint indicates the steps involved in building skills in watsonx Orchestrate.

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/1b4f44b2-bc3c-4885-90df-e3313d55d047"> 

Start with an end-to-end use case in mind and then follow this process:

1. Familiarize yourself with the best practices for skill designing skills: [Skill design content guidelines](https://www.ibm.com/docs/en/watson-orchestrate?topic=files-skill-design-content-guidelines).
2. Check whether the skill or skill flow you want to build is already available in [watsonx Orchestrate here](https://www.ibm.com/docs/en/watson-orchestrate?topic=built-in-apps).
3. Build the skills and skill flows needed to achieve the goal of your use case. 


## Developing skills

Create skills from [OpenAPI files]([https://www.ibm.com/docs/en/watson-orchestrate?topic=files-creating-skills-from-openapi](https://www.ibm.com/docs/en/watson-orchestrate?topic=adding-skills-from-files). If you don't have an OpenAPI file ready and want to build one from scratch, see [Adding skills from files](https://www.ibm.com/docs/en/watson-orchestrate?topic=adding-skills-from-files). Then, enhance the OpenAPI file into an exemplary watsonx Orchestrate [skill](https://www.ibm.com/docs/en/watson-orchestrate?topic=skills-enhancing-publishing).

After a skill is enhanced and published, it is available for you to add to your skill set from the skill catalog by following these instructions: [Adding a skill from skill catalog](https://www.ibm.com/docs/en/SSAVQO/skills/skill_addremove.html#adding-a-skill-from-skill-catalog).


**Tip:** Users with the either the Admin or Builder role can add the skill to a team skill set.


### Combining skills into skill flows
Now that the required skills are available, it's time to build your end-to-end use case as a time-saving [skill flow](https://www.ibm.com/docs/en/watson-orchestrate?topic=combining-skills-into-skill-flows ).

### Testing skills
Ensure your skills are working as expected. Test the skills by clicking them from the tiles on home page or by typing phrases into the chat bar to find the skills. Revise the skills to adhere to the [ Skill design content guidelines ]( https://www.ibm.com/docs/en/watson-orchestrate?topic=files-skill-design-content-guidelines ).

After sufficient testing, [export the skills](https://www.ibm.com/docs/en/watson-orchestrate?topic=skills-exporting).

### Pushing the skills into Github repository

Merge the skills (.json files) into your Github repository.  In the Partner Github repository, add documentation for the users of this skill to use the skills efficiently.

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/69e45726-3738-49cd-a9d3-692d64dbbdf7">

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/2f1be293-d3e6-434e-af8f-fd8adf90b09b">


### Obtaining approval
Add your test evidence, such as a screen capture of the test:

<img width="468" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/5be773ac-07e7-4a98-a8a1-dcfe22e29f65">


### Publishing the skill to be part of Watson Orchestrate Global skills catalog
In the README.md file, indicate whether you want your skills to be published by the watsonx Orchestrate team to be part of the out-of-the-box skill catalog. When they are included in the skill catalog in the subsequent release, you can test the skills on your production instance of watsonx Orchestrate.



## Building an OpenAPI from scratch

You can build an OpenAPI by using a text editor or  by using the CURL command in CDK, which is an IBM tool:

1. Log in to CDK at https://explorer.automation.ibm.com/cdk.

2.	Identify the API developer documentation for the identified set of skills or APIs, for example https://developer.webex.com/docs/api/v1/recordings. Narrow down to the exact API: https://developer.webex.com/docs/api/v1/recordings/list-recordings.

3.	Log in to Connector Development Toolkit using your IBM ID (https://explorer.automation.ibm.com/cdk). You can link any email ID as an IBMid. For partners onboarded as IBM sub-contractors, it is advisable to use a IBM w3 ID as the IBMid. 

4.	Click **Create a connector** and provide the essential details like the app name and the icon and then attach the OpenAPI specification file, if it's available. 

<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/667ef505-79bb-46b8-a48b-a9c9b8f7a16e">

5.	If an OpenAPI is not available, click **Create a connector** and complete the steps to create an OpenAPI from scratch.

Create a group (optional) to group a set of APIs together, for example a WebexRecording group:

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/f6055ad0-f967-42e9-8926-bcb3bf273c21">


6.	Create actions for the WebexRecording API by using a CURL command. Most API documentation provides CURL commands for the APIs, such as this example from Workday: 
 
 
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/79cbdeb4-5b6a-4e83-930c-c351f557bbf6">


If a CURL command is not available, get one by using PostMan:

 
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/35fced6b-7d4d-4f00-8dfa-36d4022d5dd0">



Request

https://webexapis.com/v1/recordings?from=2020-07-12T09:30:00+08:00&to=2020-07-31T09:30:00+08:00&meetingId=f91b6edce9864428af084977b7c68291_I_166641849979635652&hostEmail=john.andersen@example.com&siteUrl=example.webex.com&integrationTag=dbaeceebea5c4a63ac9d5ef1edfe36b9&topic=John's%20Meeting&format=ARF&serviceType=MeetingCenter&status=%5Bobject%20Object%5D,%5Bobject%20Object%5D

  <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/d292cb06-14e4-46c8-9062-5edb38de6593">


 

In PostMan, click the code button. 

 




7.	Copy the CURL command into the CDK and click **Add action**.

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/c6d1d762-f2f9-4310-933b-faf3aab1e193">

The ListRecording API is now created:

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/b32c2521-8f75-4dc1-ab44-41b255b4ce97">



8.	From the Request and Response tabs, change any of the fields, mark fields as mandatory, add new fields, add pagination, as you see fit:
   <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/75854a24-ffaf-4700-ad2f-98457f817de3">

 

9.	Create the response schema by copying the response example from Webex developer docs:
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/5ef42b83-8c64-4e8d-b55a-db875793037d">

 


10.	Add or remove response fields:
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/c22c70ce-01e6-4c7f-b6a4-aa80cc69138f">

 


11.	From the Connection Properties tab, add the required authentication scheme for the API, such as if Webex takes a bearer token:
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/764be1d7-1592-4919-bc5c-d5c5cd1cd6bc">

 

12.	Test the API by providing your credentials:
<img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/32d305a4-ec7f-48c7-a554-4567c885bb2d">

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/9d4d0076-767d-487a-a796-e8535dd77e51">



13.	After you connect successfully, test the APIs:

 <img width="452" alt="image" src="https://github.com/mithunkatti/skill-dev-documentation/assets/55537587/be22d15f-b428-49d0-99d8-ca4a0fb73e57">




14.	Download the app, which is call a "connector" in the Connector Development Kit.

 


15.	Decrypt the .car file to extract the raw OpenAPI needed for the watsonx Orchestrate skill by using the command you received from IBM. 

Now you can continue developing the skill.


