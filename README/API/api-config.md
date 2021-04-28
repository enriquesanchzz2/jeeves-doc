## **Jeeves API Local**
You can run a local instance of the Jeeves API for testing new projects and test cases locally, or to try out new features for the Jeeves API before deploying them to the master version. To set up a local instance of the Jeeves API on your computer, check the following steps and requirements: 

## API Requirements
These are the minimum requirements to run the Jeeves API locally on your computer: 

* Docker
* Java JDK 8
* Apache Maven 3
* An AWS S3 Bucket
* An AWS Elasticsearch 6.5 Domain
* AWS IAM Grants

<aside class="warning">Make sure you comply with the minimum requirements installed before starting to configure your Jeeves API Local Environment.
</aside>

## Configuring the API Virtual Workspace
To configure the Jeeves API Virtual Workspace on your computer, follow these instructions: 

1. Open a console window on your computer.

2. Access the location in your computer where you desire to clone the Jeeves API official repository

3. Clone the Jeeves WebApp official repository to the selected location, type the following command:
``git clone https://github.dowjones.net/SharedServices/Jeeves.API.git``

4. Access the folder of the Jeeves WebApp cloned repository
``cd path/to/Jeeves.API``

5. Load your AWS AMI credentials. To do so, follow the [Tokendito](https://github.com/dowjones/tokendito) Guide.

6. Build the docker image and container, type the following command: 
``sh docker/dockerfile-build``

7. Run the Virtual Workspace
``sh docker/compose localhost``

8. Build the API Environment
``sh build``


<aside class="success">
Once the command stops running, the Virtual Workspace of your Jeeves API Local instance has been configured.
</aside>

## Working with the API Virtual Workspace
Working with the Virtual Workspace of the Jeeves API is simple. This section presents the commands to run and stop the Virtual Workspace among other useful commands. 

### **Run the Virtual Workspace**
To run the Virtual Workspace, you have to decide first in which environment do you want to work, the following presents the available environments for the Jeeves API.

| Environment | Configuration | 
| ----------- | ------------- |
| ``localhost`` | Calls local ElasticSearch and S3 images and it forks locally a process for the test cases. |
| ``dev, nonprod, stag`` | Use the AWS Spot Architecture to function. |



Once you have selected the environment you want to work in, follow these instructions:

1. Run the Jeeves API Docker Compose container, type the following command with the env that you want to use:
``sh docker/compose <env>``

2. Once the container is running, run the API by typing the following command:
``sh run``

<aside class="success">
You successfully started the Jeeves API Local instance if your terminal presents a message like this one: <strong>"[main] INFO org.eclipse.jetty.server.Server - Started @9076ms"</strong>
</aside>

### **Stop the Virtual Workspace**
To stop the Virtual Workspace, you need to follow these instructions

1. Stop the API Running Job by pressing `CONTROL + C`

2. Exit the Virtual Workspace by typing the `exit` command

<aside class="success">
You successfully stopped the Jeeves API Local instance when your terminal presents you your common prompt line.
</aside>


### **Enter the Bash Interactive Console**
The Bash Interactive Console helps you check the Docker Container logs, information, files, and configurations. 
To use the Bash Interactive Console, type the following command just after the container has started: 
``docker exec -it jeeves.api.ps bash``

<aside class="success">
After following these steps, you can interact with the files and logs of your Jeeves API Docker container.
</aside>

 
