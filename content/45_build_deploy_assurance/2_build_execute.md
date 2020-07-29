+++
title = "Build & Execute"
chapter = false
weight = 2
+++

### PIPELINE CREATION AND EXECUTION
To deploy the pipeline, run the following commands in Cloud9’s terminal:

```bash
aws cloudformation  create-stack --stack-name PostBuildQA --template-url https://aws-wrkshp-artifacts.s3-eu-west-1.amazonaws.com/awsworkshop_infrastructure_artefacts/awsworkshop_postbuild_qa.json --capabilities CAPABILITY_NAMED_IAM
```

Go to the [CloudFormation](https://console.aws.amazon.com/cloudformation/home) console and check the status of your pipeline stack creation named 'PostBuildQA'. It should state - {{% color info %}}“CREATE_IN_PROGRESS”{{% /color %}}.

{{% notice info %}}
This step takes approximately 1 minute and if successful, you can see the status of STACK - ‘PostBuildQA’ as {{% color success %}}“CREATE_COMPLETE”{{% /color %}}, as shown in the screenshot below: 
{{% /notice %}}


![](/images/module2/module-2_p_1.png)

At this point, you should have automatically triggered, a fully functioning Post-Build-QA CodePipeline.

![](/images/module2/module-2_p_2.png)

If you head over to [CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/home) in the AWS console and click on the pipeline that begins with the name **workshop_codepipeline_PostBuildQA**, you should see the screen as shown below: 


![](/images/module2/module-2_p_3.png)

On successful execution of the pipeline you should have the working instance of your Application in the test environment. To access the application, replace the value of key ‘AppServer_PublicIP’ which you have noted from the secrets (Secrets Manager) section, of the Getting Started section in below URL 

- Application Under Test URL is - `http://< AppServer_PublicIP >:3000`


This application (refer the screenshot as shown below) has now been deployed, smoke tested and ready for functional assurance.



![Create Complete](/images/module2/module-2_3.png)



