+++
title = "Debug & Fix"
chapter = false
weight = 3
+++

#### DEBUGGING AND RE-EXECUTION

To debug the issue, from the AWSCodeBuild you can go to CodeBuild section **-->** Report History and click on the latest failed link under Test Reports History.


You can then view the below report. Click on the failed test case to see the reason for failure.

![AWS workshop Unit Test](/images/module1/Module_1-4.png)

Alternatively, please switch to your Reporting Dashboard and go to the section UnitTest to view the summary of this stage. Click on the component to view detailed test report to spot where the test failed. (This will link you to the above report)

![](/images/module1/Module1-DebugNFix.png)

Let’s understand the nature of the failure.

**What is the failure?**

One of the unit tests named **‘Register - Last name should be present’** has failed because the ID of the UI object is incorrect while the unit test was written.


Instead of **‘lastName’**, the developer has updated it to **lastName1**.

**AWS CodeBuild Logs**
![Register Test](/images/module1/Module_1-5.png)

**How to fix it?**

Go to “[AWS CodeCommit](https://console.aws.amazon.com/codesuite/codecommit/home)’ and navigate to below path:



**awswrkshp-aut-frontend -> test -> applicationcomponents -> testscripts -> unit_tests -> containers** and look for the file **Register.test.js**. This file has unit tests related to ‘registration’.

To fix this issue, go to line number `55` and change ‘**lastName1**’ to ‘**lastName**’. Refer the screenshot as shown below:
![How to Fix](/images/module1/Module_1-6.png)


Great, you have now debugged and fixed the issue. 

Provide required details such as **author name, email address** and **commit message** (change description) and click **‘commit changes’**.
![Edit a File](/images/module1/Module_1-7.png)

![Edit a File](/images/module1/Module_1-7-1.png)

The Commit Change to the **Register.test.js** file will trigger the pipeline automatically and this time, it will execute without errors. Refer the screenshot as shown below for ‘succeeded’ status updated against each stage. 


![Register Test](/images/module1/Module_1-8.png)

With the successful execution of the pipeline, you should have a working instance of your application under test, deployed in ECS. 

To access the application, replace the value of key ‘**ApplicationFrontEndURL_DevEnv**‘, which you have noted from the secrets (Secrets Manager) section, of the Getting Started section in below URL:
- Application Under Test URL is - `http://< ApplicationFrontEndURL_DevEnv>:3000`


![Register Test](/images/module1/Module_1-9.png)







