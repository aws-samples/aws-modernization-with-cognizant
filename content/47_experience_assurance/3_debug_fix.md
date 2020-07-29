+++
title = "Debug & Fix"
chapter = false
weight = 3
+++



#### DEBUGGING AND RE-EXECUTION
Security test build has failed because the X-Frame-Options was not set in the response headers and this was detected by the ZAP Proxy. This rule is set as “**FAIL**” in the gen.conf file for ZAP tool.

To verify this, go to “Report Dashboard” **-->** Go “Experience Assurance” section and Click on the “Rule Report” link under the “Security Test” section. (This will open the security_test_output.txt in browser).

If you scroll down to the bottom of the file, you will notice the failure (as shown in the image below) 

![](/images/module4/debug-1.png)


For now, consider this as a “False Positive” and let us fix these issues. 


Change the rule for X-Frame-Options Header Scanner from **FAIL** to **WARN**, so that the security test will pass with the warning and the code progresses to the next build step.
  


Go to “[AWS CodeCommit](https://console.aws.amazon.com/codesuite/codecommit/home)’ **-->** Open the “awswrkshp-tests-security” repository. Locate and open the “**gen.conf**” file. This will have the set of passive security scan rules to be validated.

![](/images/module4/debug-2.png)

Click on “**Edit**”.

Change the rule for X-Frame-Options Header Scanner from **FAIL** to **WARN**. Refer the screenshot  as shown below for details:

![](/images/module4/debug-3.png)

Scroll down to the bottom of the page and provide the required details like **author name, email address** and **commit message** (change description) and click ‘**commit changes**’.

The Commit Change to the **gen.conf** file will trigger the pipeline automatically and this time security testing build will be executed without any errors.

The ‘succeeded’ status is now updated for each stage, as shown below:

![](/images/module4/debug-4.png)





