## **Deploying Jeeves API**
If you have made changes to the Jeeves API interface, or created and added new features, then, you need to deploy a new version of the Jeeves API to the cloud so everyone can have access to these new features. To deploy a new version of the Jeeves API, follow these instructions:

## Run the API Jenkins Job
To start the deployment of the Jeeves API new features, you need to run the Jenkins Job responsible for deploying them. To run the Jenkins Job, follow these instructions:

1. In your Okta Verify App, generate a single-use token
2. Go to the Dow Jones Jenkins Dashboard
3. Log in with your username and your Okta single-use token
4. Type in the search bar the name of the project: `jeeves-api-deploy`
5. Select the environment where you want to deploy the changes: `nonprod` or `stag`
6. Execute the Jenkins Job

## Monitor the API Deployment
Once the Jenkins Jobs is running, you can monitor the process by watching the Elastic Beanstalk Events in your AWS Console. To check the process, follow these instructions:

1. In your Okta Dashboard, select the **AWS CON** App
2. Select the Account of the environment where you started the Jeeves API Deployment Jenkins Job, the available accounts are the following:

    | Environment | Account |
    | ----------- | ------- |
    | nonprod | djamznconnonprodshdsvc (827737064932) |
    | stag | djamznconstagshdsvc (044809175532) |

3. Click **Sign-in**
4. On the top left side of the menu bar,  set the location to **US East (N. Virginia)us-east-1**
5. Click on the **Services** Menu on the upper left side of the page
	A dropdown menu appears
6. In the dropdown menu, select **Elastic Beanstalk**
    It redirects you to the Elastic Beanstalk home page

    <aside class="notice">Tip: You can also search for <strong>Elastic BeanStalk</strong> in the <strong>Search Bar</strong>.</aside>

7. In the menu on the left side of Elastic Beanstalk home page, select  the **Environments** option
    A list with all the environments available appears on the right side of the page
8. Select the `jeeves.api.<env>` environment from the list
    It redirects you to the home page of the environment
    <aside class="notice">Tip: You can use the search bar at the top of the list to filter the environments.</aside>
9. On the menu at the right side of the environment home page, select **Events**
    It redirects you to the Events page with the recent events of the environment.
    <aside class="notice">Tip: Alternatively, you can scroll to the bottom of the environment Home page and check the <strong>Recent Events</strong> panel.</aside>

The AWS Elastic Beanstalk Environment console also presents the health of the deployment on each Environment Home page. Alternatively, you can check the health of the deployment following the steps in the section [Check the API Deployment Health](#check-the-api-deployment-health).

## Check the API Deployment Health
Once the deployment has been completed, you can check its health through the AWS Elastic Beanstalk Environment Home page, or by opening in your browser the Deployment Health Script Link of the environment where you deployed your changes. Below you can find the links to each of the environments available: 


| Env | Url |
| --- | --- |
| `nonprod` |http://jeeves-api-nonprod.us-east-1.elasticbeanstalk.com/_health |
| `stag` | http://jeeves-api-stag.us-east-1.elasticbeanstalk.com/_health |


```shell
{
"deployed": "Wed, 24 Mar 2021 14:31:53 GMT",
"health": "ok"
}
```
Once the browser opens the link for the Environment Health Check, you should see the following script:

The variables represent the following information:

* **`deployed`:** Presents the date in which the current version of the Jeeves API was deployed 
* **`health`:** Presents the health of the current version of the Jeeves API
