## **Jeeves WebApp Local**
You can run a local instance of the Jeeves WebApp for testing locally new projects and test cases, or new features for the Jeeves WebApp before deploying them to the master version. To set up a local instance of the Jeeves WebApp on your computer, check the following steps and requirements:

<aside class="warning"> To run a local instance of the Jeeves WebApp in your computer, you need to configure first the <a href="#jeeves-api-local ">Jeeves API Local environment</a>
</aside>

## WebApp Requirements
These are the minimum requirements to run the Jeeves WebApp locally on your computer: 

* Jeeves API configured locally
* Node version 10.15 LTS or superior
* npm version 3.10 
* GlobalProtect connected to the DowJones VPN

<aside class="warning"> Make sure you comply with the minimum requirements installed before starting to configure your Jeeves API Local Environment.
</aside>

## Configuring the WebApp Virtual Workspace
To configure the Jeeves WebApp Virtual Workspace on your computer, follow these instructions: 

1. Open a console window on your computer.

2. Access the location in your computer where you desire to clone the Jeeves WebApp official repository
``cd path/to/your/location``

3. Clone the Jeeves WebApp official repository to the selected location, type the following command:
``git clone https://github.dowjones.net/SharedServices/Jeeves.WebApp.git``

4. Access the folder of the Jeeves WebApp cloned repository
``cd path/to/Jeeves.WebApp``

5. Download the Developer Node Modules, type the following command:
``npm install``

6. Run the Development Server, type the following command:
``npm run serve:dev ``

    <aside class="notice">By default, the server runs in the <strong>localhost</strong> environment.</br> 
    To work in a different environment configuration, add the <strong>ENV</strong> variable before the command:</br>
    <strong>"ENV=nonprod npm run serve:dev"</strong></br>
    </br>
    The environments you can chose from are: <strong>localhost, nonprod, and stag.</strong>
    </aside>


7. Create the docker container of the environment, type the following command:
``sh docker/dockerfile-build``

    <aside class="notice">You need to create the container just once.</aside>

<aside class="success">
Once the command stops running, the Virtual Workspace of your Jeeves WebApp Local instance has been configured.
</aside>

## Working with the WebApp Virtual Workspace
Working with the Virtual Workspace of the Jeeves WebApp is simple. This section presents the commands to run and stop the Virtual Workspace among other useful commands. 

### **Run the Virtual Workspace**
Once you have created the container, run it by typing the following command, you can change the <env> variable for the environment you need:
``sh docker/dockerfile-run <env> &``
<aside class="success">
You successfully started the Jeeves WebApp Local instance if your terminal presents a message like this one: <strong>"Server running on http://localhost:80"</strong>
</aside>


### **Stop the Virtual Workspace**
To stop the docker container, type the command:
``sh docker/dockerfile-clean``
<aside class="success">
You successfully stopped the Jeeves WebApp Local instance when your terminal presents you your common prompt line.
</aside>

### **Enter the Bash Interactive Console**
The Bash Interactive Console helps you check the Docker Container logs, information, files, and configurations. 
To use the Bash Interactive Console, type the following command just after the container has started: 
``docker exec -it jeeves.webapp.ps bash``
<aside class="success">
After following these steps, you can interact with the files and logs of your Jeeves API Docker container.
</aside>

</br>
</br>

 <aside class="warning">Remember to configure the Jeeves API environment locally before using the Jeeves WebApp. To configure it, follow the steps in the <a href="#jeeves-api-local">Jeeves API Environment Configuration Guide</a>.</aside>


