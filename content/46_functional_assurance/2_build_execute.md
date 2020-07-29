+++
title = "Build & Execute"
chapter = false
weight = 2
+++


#### PIPELINE CREATION AND EXECUTION

{{% notice note %}}
Please complete the Module 2: Post-Build QA before commencing with this module. This will ensure you have deployed the build on the server successfully before executing the Functional test suits during this module.
{{% /notice %}}


Execute the cloud formation template from Cloud9 to automatically create the Functional Assurance pipeline.

```bash text
aws cloudformation  create-stack --stack-name FunctionalAssurance --template-url https://aws-wrkshp-artifacts.s3-eu-west-1.amazonaws.com/awsworkshop_infrastructure_artefacts/awsworkshop_functional_assurance.json --capabilities CAPABILITY_NAMED_IAM
```

Go to the [CloudFormation](https://console.aws.amazon.com/cloudformation/home) console and check the status of your pipeline stack creation named 'FunctionalAssurance'. It should state - {{% color info %}}“CREATE_IN_PROGRESS”{{% /color %}}

{{% notice info %}}
This step takes approximately 1 minute and if successful, you can see the status of STACK - 'FunctionalAssurance' as   {{% color success %}}“CREATE_COMPLETE”{{% /color %}}, as shown in the screenshot below: 
{{% /notice %}}


![Functional Assurance](/images/module3/Module_3-1.png)

On successful creation of the pipeline, the CFN will auto trigger the execution. You can now view the execution progress by navigating to [CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/home) and selecting - codepipeline_Functional_Assurance.


![Pipelines](/images/module3/Module_3-2.png)


 You will notice that the Pipeline fails at the UI_Test and RWD_Test.

![Pipelines Functional Assurance](/images/module3/Module_3-3.png)

Let us debug, fix the issue and re-execute the pipeline.

{{% notice recommended %}} 
Additionally, Practitioners can access Cognizant Thought Leadership on CI/CD for Web Services Testing, by referring the insightful whitepaper by our technology experts titled - **“Continuous Integration and Continuous Delivery to Facilitate Web Service Testing”**.  You will find the link to the whitepaper in the Register with Cognizant page -[https://www.cognizant.com/application-modernization](https://www.cognizant.com/application-modernization). 
{{% /notice %}}

