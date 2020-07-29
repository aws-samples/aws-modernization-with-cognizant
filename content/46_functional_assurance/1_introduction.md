+++
title = "Introduction"
date = 2019-08-11T19:21:12-07:00
weight = 1
chapter = false
+++


#### Objective: To validate application's functional behavior such as business process, user workflows & regression impact against the pre-defined outcomes
Functional behaviors are “what” the system should do. Functional testing evaluates if functions perform as expected. Functional requirements may be described and documented in business requirements specifications, epics, user stories, use cases, (or) functional specifications, or they may be undocumented. 

These tests should be performed at all test levels, though the focus is different at each level. For our particular use case, we will focus on the following
- UI focuses on validating business process through screens and objects
- API focuses on back-end services leveraged by front-end elements and objects
- Mobile refers to an RWD (Responsive Web Design) based interfaces



![Testing Scope](/images/module3/Module_3.png)


#### PIPELINE OVERVIEW
This module will walk you through the assurance of your application functionalities. You will learn how to execute UI-based tests, responsive web design (RWD)-based tests and API tests with an open source tool stack.  


![](/images/module3/intro-1.png)


The Functional Assurance pipeline consists of two stages viz. source and build.

With every code change committed to the repository, the pipeline will trigger all the three tests in a parallel i.e. UI based testing, RWD testing and API testing tests. Various dependencies and commands required for respective tests are defined in the buildspec.yml file in the source code repository. 

Automation for UI on desktop and mobile with RWD tests is implemented using open source tools – Selenium, Cucumber and Maven following Page Factory Pattern:

- **UI Automation**: Ten test cases will be executed using AWS CodeBuild and the results will be saved in the directory - awswrkshp_functional_assurance_ui/target/extent-reports in the target s3 bucket.

- **RWD  Automation**: Five test cases will be executed on mobile compatible application rendered on Chrome web browser and results will be saved in the directory - awswrkshp_functional_assurance_ui_rwd/target/extent-reports in the target s3 bucket.

- **API Tests**: API based test automation is implemented using the open source tools like Rest-Assured, Maven and Cucumber. Ten test cases will be executed on the AWS CodeBuild and the results will be saved in the directory - awswrkshp_functional_assurance_api /target/extent-reports in the target s3 bucket.




