+++
title = "Introduction"
date = 2019-08-11T19:21:12-07:00
weight = 1
chapter = false
+++


#### Objective: To execute the continuous testing pipeline with all the pre-defined quality gates 


In prior modules, you have seen how tests are required to verify all facets of the application viz. – functional, performance, security, accessibility etc. You have also seen the need for quality assurance for not just the UI, but also at a component level viz. – code, build, deployment, data & interfacing services. You have seen a few examples of application defects and test incidents that can occur during a test pipeline execution and understood how to fix them.





![](/images/module5/module-5.png)





### PIPELINE OVERVIEW

{{% notice warning %}} 
If you have commenced the workshop from this module, you will encounter 3 failures while executing the end-to-end pipeline. Please refer **‘Build and Execute’** and **‘Debug & Fix’** sections of **Module 1**, **Module 3** and **Module 4** to understand these failures and how to fix them.
{{% /notice %}}

 
In this fifth and final module, you will execute all the same tests executed as the part of previous modules, but in a continuous testing pipeline from code commit to final reports. Additionally, in this module you will also read about new-age QA practices like, AI driven QA that are increasingly becoming critical for modern-day testing in DevOps.

**End-to-end Quality Assurance Code Pipeline consists of the following stages and components:**
 
•	**Source Stage** – contains source code for all the subsequent stages i.e. application source code for front-end and back-end, functional test code for Smoke, API, UI and RWD testing types and code for experience assurance testing types, namely – performance, security and accessibility.
 
•	**Pre-Build Quality Check** – induces static code quality measures on both the front-end and back-end components of application under test for continuous inspection of code quality to detect bugs, code smells and security vulnerabilities.
 
•	**Unit Test** – pipeline further has a robust suite of unit tests, complimented by code coverage techniques to give actionable guidance and identify any critical slips.
 
•	**Build** – if no issues are detected in the pipeline at unit testing stage, process continues further by building and packaging the application.
 
•	**Deploy to Test** – on successful build, AWS Systems Manager is leveraged to deploy back-end and front-end components of the application to EC2 instance.

•	**Post Build Quality Check** – runs smoke test to qualify the build for further stages of testing.

•	**Functional Assurance** - evaluates functional behaviours i.e. “what” the system should do (or) if the application / system functions perform as expected by executing a comprehensive set of APIs, UI and RWD tests as parallel CodeBuild jobs.

•	**Experience Assurance** - evaluates non-functional behaviours i.e. “How” the system should perform its functions by executing performance, security and accessibility tests as sequential CodeBuild jobs.



![text](/images/module5/p-1.png)
