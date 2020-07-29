+++
title = "Debug & Fix"
chapter = false
weight = 3
+++


#### DEBUGGING AND RE-EXECUTION

To understand in detail of why this failure has happened and check the error message go to Reporting Dashboard and navigate to: MODULE 3 # FUNCTIONAL ASSURANCE -> Regression Test - UI -> Click on the **“Detailed Report”**. 

You will be able to see the report with the error:

![](/images/module3/module_3-debug.png)

Click on the failed Test Case (TC) to read the error message. 

`< org.openqa.selenium.NoSuchElementException: no such element: Unable to locate element: {"method":"css selector","selector":"#productsearch"} >`

Such errors indicate that the automation script is unable to locate the object on the screen as properties of that UI object have seemingly changed since the last build. This is a very common error and calls for script maintenance.

To fix this issue, navigate to [CodeCommit](https://console.aws.amazon.com/codesuite/codecommit/home), find the repository **“awswrkshp-functional-assurance”** and edit the file ShopProductsPage.java **awswrkshp-functional-assurance/src/test/java/pages/ShopProductsPage.java**

Refer the screenshot as shown below for details:


![AWS Functional Assurance](/images/module3/Module_3-4.png)

You will notice at line# 25 as: @FindBy(id = "productsearch1")
Change the productsearch1 to productsearch

Provide the required details like **author name**, **email address** and **commit message** (change description) and click **‘commit changes’**
. 
![Commit Changes](/images/module3/Module_3-4-1.jpg)
The Commit Change will automatically trigger the pipeline and this time it will be executed successfully. Refer the screenshot as shown below for ‘succeeded’ status updated against each stage.

![CodePipeline Functional Assurance](/images/module3/Module_3-5.png)






