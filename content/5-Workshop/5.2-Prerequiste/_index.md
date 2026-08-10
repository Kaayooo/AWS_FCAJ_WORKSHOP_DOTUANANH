---
title : "Prerequisites"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

#### Prerequisites

Before starting this workshop, make sure you have:

- An AWS account with access to create IAM roles, S3 buckets, Lambda functions, Glue resources, and Amplify applications.
- A chosen AWS region such as us-east-1 or ap-southeast-1.
- AWS CLI installed and configured.
- Python 3.11 or later, plus Git.
- A basic understanding of the services introduced in the worklog weeks: S3, IAM, Glue, Athena, Lambda, EventBridge, and Step Functions.

#### Suggested permissions

At minimum, your IAM principal should allow access to:

- S3: create and manage buckets and objects
- IAM: create roles and policies
- Lambda: create and invoke functions
- Glue: create crawlers, jobs, and databases
- Athena: query data in the catalog
- EventBridge and Step Functions: schedule and orchestrate workflows
- Amplify, Cognito, API Gateway, SES, and CloudWatch for the deployment phase

#### Preparation checklist

1. Create a dedicated AWS account or use your training account.
2. Configure AWS CLI with your access keys.
3. Choose the target region and keep it consistent throughout the workshop.
4. Prepare a project name such as financial-distress-platform.
5. Review the proposal architecture so you can map each lab step to the corresponding AWS service.

In this lab, we will use **N.Virginia region (us-east-1)**.

To prepare the workshop environment, deploy this **CloudFormation Template** (click link): [PrivateLinkWorkshop ](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateURL=https://s3.us-east-1.amazonaws.com/reinvent-endpoints-builders-session/Nested.yaml&stackName=PLCloudSetup). Accept all of the defaults when deploying the template. 

![create stack](/images/5-Workshop/5.2-Prerequisite/create-stack1.png)

+ Tick 2 acknowledgement boxes
+ Choose **Create stack**

![create stack](/images/5-Workshop/5.2-Prerequisite/create-stack2.png)

The **ClouddFormation** deployment requires about 15 minutes to complete.

![complete](/images/5-Workshop/5.2-Prerequisite/complete.png)

+ **2 VPCs** have been created

![vpcs](/images/5-Workshop/5.2-Prerequisite/vpcs.png)

+ **3 EC2s** have been created

![EC2](/images/5-Workshop/5.2-Prerequisite/ec2.png)