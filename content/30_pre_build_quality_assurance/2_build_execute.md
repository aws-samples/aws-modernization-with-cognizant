+++
title = "Build & Execute"
chapter = false
weight = 2
+++

#### PIPELINE CREATION AND EXECUTION

To deploy the pipeline, run the following commands in Cloud9’s terminal:

```bash text
aws cloudformation  create-stack --stack-name PreBuildQA --template-url https://aws-wrkshp-artifacts.s3-eu-west-1.amazonaws.com/awsworkshop_infrastructure_artefacts/awsworkshop_prebuild_qa.json --capabilities CAPABILITY_NAMED_IAM
```

Go to the [CloudFormation](https://console.aws.amazon.com/cloudformation/home) console and check the status of your pipeline stack creation, named 'PreBuildQA'. It should state - {{% color info %}}“CREATE_IN_PROGRESS”{{% /color %}}.

{{% notice info %}}
This step takes approximately ~1minute and if successful, you can see the status of STACK - ‘PreBuildQA’ as {{% color success %}}“CREATE_COMPLETE”{{% /color %}}, as shown in the screenshot below: 
{{% /notice %}}







![Cloudformation](/images/module1/Module_1-1.png)

Please click on your stack name. Under Outputs tabs, details of the key services created will reflect. Refer the screenshot as shown below:

![AWS workshop prebuildqa](/images/module1/Module_1-2.png)

All the necessary details are also added in AWS Secrets Manager as Secrets, so that these values can be utilized throughout the various components that we will build as the part of this workshop.

At this point, you should also have an automatically triggered, fully functioning Pre-Build-QA CodePipeline. 

If you head over to [CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/home) in the AWS console and click on the pipeline that begins with the name workshop-**codepipeline_prebuildqualitycheck**, you should see the screen as shown below: 


![AWS workshop prebuild quality check](/images/module1/Module_1-3.png)

You will notice that the Pipeline fails at the UnitTest stage - ReactAppUnitTest and thus the subsequent steps (Build and Deploy to Fargate) are not executed.

Let us debug and fix this issue to re-execute the pipeline and then see the impact on subsequent stages.





