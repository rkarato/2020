## The AWS Developer Challenge for Data Engineers
### Instructions

In general feel free to expand/change the challenge in any way you like, just explain your solution and decision making, any concerns around it or limitations etc.

Some information/content is left out intentionally to validate your working experience, please fill in the missing parts.

> Fork this repo with your solution. Ideally, we'd like to see your progression through commits, and don't forget to update the README.md to explain your thought process.

**Please do not reference any websites or published articles. We are looking for original content!**

Please let us know how long the challenge took you. We're not looking for how fast or detailed you are. It's just to give us a clearer idea of what you've produced in the time you decided to take. Feel free to go as big or as small as you want.

### AWS Data Engineer | Challenge Information

This company is ingesting data into a 'data lake' running AWS. Below find a picture of the AWS components used for this company's architecture. 

![AWS-COMPONENTS](/media/awscp.png)

## Section A
### Design an Architecture Diagram - We want to see a picture.
Use the components shown above and create an architecture with your tool of choice (powerpoint / draw.io / etc) showing how to ingest data from an on-premise site into AWS. 

Upload the diagram/picture into the Git repository and indicate where it's saved. Use the given components as far as possible to illustrate your solution.

##### Hints
* Focus on *low cost & high* performance.
* All the data are stored in S3 buckets.
* Athena is used to query the data.
* Show how you will use Step Functions to orchestrate the *ingest* process.
* AWS DynamoDB / CloudWatch must be used.
* Glue Jobs should be used to do the ingest.
* CloudFormation output is a CodeBuild Project
* Git is used to save the terraforms and python / pyspark code.
* You do not have to design/depict the CI/CD, assume that it's already in place.
* Look at the available .tf files to get an understanding of the architecture.
___

## Section B
### Describe the Section A - Architecture Diagram 

Within this Readme.md describe the architecture above, giving detail when and how you would use the selected components.

**Please do not reference any websites or published articles.** 
**We are looking for original content!** 
**We do not want to see definitions of the AWS components.**


##### Hints
* Consider aspects like security (iam / firewalls / vpc / security groups / roles)
* To each component used, give a detailed description on how it fits into the solution, please do not reference existing AWS documentation, use your own words! Feel free to document your thought process. We are interested to find out how you think.
___

## Section C
**Try your best do not keep the section open, we want to see how you apply yourself**

Within the Git Repository Structure:
* Modify the CloudFormation Template [CFN/seed.yaml] in order to create a CodeBuild Project.
* Update the _glue_jobs.tf_, _main.tf_ and _output.tf_ terraform files. 
* Provide the python script that will be used within the glue job, using either python shell or spark, think here about using DynamoDB to keep certain job settings and table structures for S3.
___

## Submit it

Please use a private repo just email us when you are done. 

## Your Solution Starts HERE!!!
Use this area to describe your solution as requested in *_Section B_*. 
## Architecture
![AWS-ARCHITECTURE](/media/Architecture.png)
The diagram above ilustrates the serverless data pipeline.
Data from an on premises database is uploaded to the cloud, landing into the company's the Data Lake.
To facilitate the orchestration of the services used in this pipeline, step functions are used to control the different stages of the processing and provide a visual representation of the modules and state of execution



### Services used:
#### Cloud Watch
Integrates with Step Functions and enables scheduling for workflows. Also keeps logs of all the AWS services.

#### Step Functions
Manages workflows between services, state changes and human interactions

#### Lambda
Simple way to run code based on different languages, without managing servers. 

#### Glue
AWS ETL tool. Uses spark technology and has good integration with a number of other AWS services.

#### SNS
Used to send messages to different destination. The messages are queued and sent to subscribers that will translate them into email, SMS, http requests, etc.

#### Systems Manager
Service that provides a centralized repository for common configuration values. Also provides tools to facilitate administration of systems like combined monitoring and troubleshooting.

#### Secrets Manager
Service similar to Systems Manager capability of controling configuration information. It has more sofisticated mechanisms to safe guard sensitive infomrtion, encryption and rotation mechanisms

#### S3
Basic storage service of the AWS space. Cheap, reliable and integrated with all services that require long term storage.

#### IAM
Core services to control security and access to all AWS resources.

#### Athena
SQL interface to data stored in S3 and a few other services. The data is required to have a schema definition for the SQL engine to be able to function.

#### VPC 
It's the logical network organization of the AWS resources. It's correlated to the network setup of a physical to a data center.

#### Generic Database
The representation of a RDBMS data source present on premises.


## Deployment
![AWS-DEPLOYMENT](/media/Deploy.png)


## Additional Comments / Information / Concerns
Add info here.
