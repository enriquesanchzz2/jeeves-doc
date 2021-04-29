# Jeeves Structure and Cloud Architecture
Jeeves is built on top of the Gatling Open Source Library, and it implements AWS Elastic Beanstalk for running the Test Cases. 


## Project Structure
Thi section presents an script with the structure of a Jeeves Project. 

Jeeves project structure:

```
.
│ env - The available environment configurations.
│
│ terraform - The Jenkins and Terraform scripts for deployment.
│
│ jeeves_home
│
├── jeeves.core  - The shared business logic and utilities.
│
├── jeeves.tests
│   ├── src/main
│   │   ├── jeeves.tests.SimulationWorker
│   │   │   The entry point when a testcase is launched. In charge of:
│   │   │   (1) Loading the testcase data to the filesystem.
│   │   │   (2) Running the testcase.
│   │   │   (3) Storing the report and statistics.
│   │
│   ├── src/test - The Gatling code for the testcases.
│   │
│   └── config   - The Jeeves configuration for the testcases.
│
├── jeeves.api
│   ├── src/main/scala
│   │   ├── jeeves.api.Routes     - These routes expose the Jeeves functionality.
│   │   ├── jeeves.content.Routes - These routes expose content files, such as reports.
│   │
│   └── src/main/webapp
│   │   ├── swagger/v2/swagger.json - Documentation for the API Routes.

```

## 2. Cloud Components

With the Spot Agent, Jeeves launches testcases in an AWS VPC
The image presents the AWS structure of Jeeves.

![jeeves 4 4 0 - run agent_ spot](https://github.dowjones.net/storage/user/1457/files/722f7942-e73a-11e8-85b1-17dcb3835234)