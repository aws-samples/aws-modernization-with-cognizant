+++
title = "Build & Execute"
chapter = false
weight = 2
+++


#### PIPELINE CREATION AND EXECUTION

To deploy the pipeline, run the following commands in Cloud9’s terminal

```bash text
aws cloudformation  create-stack --stack-name E2EAssurance --template-url https://aws-wrkshp-artifacts.s3-eu-west-1.amazonaws.com/awsworkshop_infrastructure_artefacts/awsworkshop_e2e_assurance.json --capabilities CAPABILITY_NAMED_IAM
```



Go to the [CloudFormation](https://console.aws.amazon.com/cloudformation/home) console and check the status of your pipeline stack creation named 'E2EAssurance'. It should state - {{% color info %}}“CREATE_IN_PROGRESS”{{% /color %}}


{{% notice info %}}
This step takes approximately 1 minute and if successful, you can see the status of STACK - ‘E2EAssurance’ as {{% color success %}}“CREATE_COMPLETE”{{% /color %}} as shown in the screenshot below: 
{{% /notice %}}



![Pipeline](/images/module5/module-5-1.png)

At this point, you should have automatically triggered a fully functioning End-to-End-QA CodePipeline.


Head over [CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/home) the AWS console and click on the pipeline that begins with the name workshop- **workshopcodepipelineE2E**, you will see the screen as shown below: 



![Pipeline](/images/module5/module-5-2.png)

Click on the pipeline and you will see the complete End-to-End (E2E) Assurance Pipeline. 

![Pipeline](/images/module5/build-3.png)

As a result, of the complete pipeline being executed successfully, you should have the working instance of you Application under Test deployed in EC2 instance.

To access the application, replace the value of key ‘**AppServer_PublicIP** ‘ which you have noted from the secrets (Secrets Manager) section of Getting Started section in below URL:
- Application Under Test URL is  -  `http://< AppServer_PublicIP >:3000`


![Pipeline](/images/module5/module-5-4.png)