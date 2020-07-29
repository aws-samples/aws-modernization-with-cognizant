+++
title = "Introduction"
chapter = false
weight = 1
+++

#### Objective: To assure quality of the code committed before the build creation

In software development, build refers to the process of converting files and other assets under developer's responsibility into a software product in its final (or) consumable form. These activities cover:
Compile source files **->** Package compiled files into compressed formats (like jar, zip) **->** Produce installer’s **->** Create (or) update Database schema (or) data


In DevOps, tests are designed and automated even before the code is written. To deliver quality at speed, developers execute a series of automated test cases prior to committing the code to a repository. This helps to identify any issues or vulnerabilities much earlier in the lifecycle, thereby engineering quality into the code as it progresses.

![Testing Scope](/images/module1/Module_1.png)


#### PIPELINE OVERVIEW

In this section, you will learn how to execute static code analysis, unit testing, sanity UI testing and measure code coverage with an open source tool stack.  

![Pipeline](/images/module1/module1_pipeline.png)

**The Pre-Build Quality Assurance CodePipeline consists of the following stages and components:**
1. **Source Stage** monitors changes to below source code repository for any new commits:
    - **FrontEndReactApp** – Code for front-end application
    - **BackEndSpringBootApp** – Code for back-end micro services. 
    
Every code Commit will trigger the CodeBuild job. 


2.	**Pre-Build Quality Check** uses SonarQube for continuous inspection of code quality and perform automatic reviews with static code analysis to detect bugs, code smells and security vulnerabilities for both front-end and back-end code. 
Separate CodeBuild jobs i.e. **ReactAppSonarCheck** and **SpringBootSonarCheck** are created to induce static code quality measures on both the components of application under test.

3.	**Unit Test** is a series of tests configured as CodeBuild actions i.e. **ReactAppUnitTest** and **SpringBootUnitTest** that validate all parts of the application under test. In case of issues, this phase of the CodePipeline process is ended with a failure status. If no issues are detected, the pipeline proceeds to the build stage.
Enzyme and Jest libraries are used for unit testing of the front-end. Similarly, Junit and Mockito is used for the back-end micro services.  

This stage is also complimented with code coverage tools such as Jacoco for back-end and Jest for front-end code for actionable guidance and identifying critical slips. You will be able to see the status of these tests on the reporting dashboard and the code coverage on SONARQube dashboard.

4.	**Build** commences with the creation of Docker image for front-end applications. When a new Docker image is successfully built, it is pushed to Amazon ECR.

5.	**Deploy to Fargate** deploys the image created in the build stage to AWS Fargate cluster, which spins up the following two containers -. **frontendapplication** and **virtualizedbackend** with the latest image.
At this stage, front-end application is pointing to a virtualized back-end so that tests can be executed without back-end dependencies - one of the key advantages of virtualization.

A portion of developers’ UI tests are also executed using playwright and Jest at this stage to ensure the front-end image is properly built and running along with virtualized back-end.

ECS and the Application Load Balancer will continuously monitor the health of the container and the application and will always make required adjustments to keep optimal healthy container tasks running. 

{{% notice recommended %}} 
Additionally, Practitioners can access Cognizant Thought Leadership on Containers for DevOps, by referring the comprehensive whitepaper by our technology experts titled - **“Using Containers to More Effectively Manage DevOps Continuous Integration”**. You will find the link to the whitepaper in the Register with Cognizant page - [https://www.cognizant.com/application-modernization](https://www.cognizant.com/application-modernization).
{{% /notice %}}



