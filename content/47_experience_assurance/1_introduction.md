+++
title = "Introduction"
date = 2019-08-11T19:21:12-07:00
weight = 1
chapter = false
+++


#### Objective: To validate application’s non-functional behavior such as performance, accessibility & security meet acceptable / pre-defined benchmarks


Non-functional behaviors are “How” the system should perform its functions. In today’s digital age, it’s not just about if an application works, but more importantly, how it works. Testing an application to validate its performance, security and accessibility is commonly known as Non-functional Testing (NFT). 

Shift left with NFT, allows developers / testers to leverage scaled-down environments for non-functional testing at a component level as and when, they are developed. The re-use of open source frameworks and functional automation scripts to perform early NFT, reduces the overall vulnerabilities in later stages. Additionally, Application Performance Management (APM) for end-to-end monitoring, alert mechanism and virtualization techniques, ensure continuous Non-Functional Testing.

Non-Functional Testing in DevOps is integrated across the lifecycle, here are few typical use cases:
- During build phase, it includes code-quality analysis, code profiling, single user performance validation etc.
- During environment setup, it covers automatic spin-off, off load generation environment, automatic environment configuration and test execution.
- During functional testing, it leverages automation scripts for client-side performance and accessibility assessments.



 

![Testing Scope](/images/module4/intro-1.png)



#### PIPELINE OVERVIEW

In this module, you will explore how experience is assured with non-functional testing. In digital, customer experience is critical for success and non-functional aspects play a significant role in an application’s functionality. You will see how an application’s performance, security and accessibility are validated in continuous pipeline with an open source tool stack.

![Pipeline](/images/module4/pipe-1.png)

The Experience Assurance pipeline consists of two stages viz. source and build.

With every code change committed to the repository, all three tests will be triggered in a sequence. Various dependencies and commands required for these tests are defined in the buildspec.yml file in the source code repository. 

**Performance Tests** are executed with the open-source tool Jmeter (version 5.1.1). The tests will run with five concurrent users and results will be saved in the directory “performance_test_results” in the target s3 bucket.

 Performance Tests source files:
- **AWSWrksp_NFTPerformance_Scenario.jmx** – jmeter scenario file with required transactions.
- 	data_*.csv files – input data files to be used inside jmeter scenario during runtime (such as credentials, sample credit cards, product names). 
- **.py files** – a set of python files to send data to result dashboard and to pass / fail the build run based on few conditions such as response time SLA and transaction failures.

 **Security Tests** are triggered via the open-source tool owasp ZAP. These tests will perform a passive baseline security scan with predefined rules against the given URL and save the results under “security_test_results” in the target s3 bucket.

Security Tests source files:
- **gen.conf** – List of passive scan rules to be used by ZAP proxy during runtime.
- **.py files** -  a set of python files to send data to result dashboard and to pass / fail the build run based on rule failures (as defined in gen.conf file).

**Accessibility Tests** are run using Selenium and AXE tool to analyze the application’s response against accessibility guidelines. Here, accessibility checks are done on steps executed by Selenium scripts (for each page that is rendered) and results are displayed under “accessibility_test_results” in the target s3 bucket.

Accessibility Tests source files:
- **Selenium project files**  – with a simple scenario and AXE tool dependencies in pom.xml to validate the accessibility in each step.


