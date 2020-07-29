+++
title = "Introduction"
date = 2019-08-11T19:21:12-07:00
weight = 1
chapter = false
+++

#### Objective: To check the readiness of the build for testing and preparing the environment for subsequent test executions
In this stage, developers and testers focus on a set of tests adequate to ensure critical functionalities work as required in the build and  these tests are also known as build verification testing, confidence testing (or) build acceptance testing.  

![Testing Functionalities](/images/module2/Module_2.png)


#### PIPELINE OVERVIEW

In this module, you will explore the Post Build Quality Assurance stage of the overall testing pipeline for DevOps. This stage is key in confirming the deployed build is stable (or) not and the purpose of the assurance carried out here is to confirm if the QA team can proceed with further testing.

**Post-Build Quality Assurance flow:**

![Testing Functionalities](/images/module2/module-2_pipe.png)

This module consists of two stages viz. **Code Deployment** and **Smoke Testing**. 
- **Deployment of Application:** Leverage AWS System Manager for deploying back-end and front-end components of the application under test. This is achieved via SSM Document which executes remote deployment run commands on the associated EC2 instances.

- **Smoke Testing:** Balanced mix of API and UI based test automation in the form of Smoke (or) Build Verification Test is implemented using the open source tools like Selenium and RestAssured with BDD Cucumber Framework. The test scripts will be executed using AWS CodeBuild and the results will be saved in the directory awswrkshp_build_deploy_assurance_smoke/target/extent-reports in the target s3 bucket.



