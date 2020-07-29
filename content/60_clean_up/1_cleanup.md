+++
title = "Clean-up Activities"
chapter = false
weight = 1
+++

When you are ready, just follow these last two steps to clean up the resources that were setup just for this workshop.

In order to prevent charges to your account, we recommend cleaning up the infrastructure that was created. If you plan to keep things running, so you can examine the workshop a bit more, then please remember to do the clean-up when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges. 

Copy, paste and execute the following commands into Cloud9’s terminal in sequence to commence the clean-up activity. 


```bash
wget https://aws-wrkshp-artifacts.s3-eu-west-1.amazonaws.com/awsworkshop_infrastructure_artefacts/awsworskhop_cleanup_environment.sh
```

```bash
chmod +x awsworskhop_cleanup_environment.sh
```

```bash
./awsworskhop_cleanup_environment.sh
```

{{% notice info %}}
This complete step takes approximately 5 minutes and if successful, you should see the following relevant messages for each command:
{{% /notice %}}



![](/images/cleanup/1.jpg)

In the [AWS console](https://aws.amazon.com/console/), go to [CloudFormation](https://console.aws.amazon.com/cloudformation/home) and verify that none of the stacks are listed in CloudFormation and then you are done.

Finally, close the Cloud9 window and manually delete your Cloud9 environment. Please follow the below steps:
- In the AWS console, navigate to [Cloud9](https://console.aws.amazon.com/cloud9/home). 
- Select your Cloud9 Environment
- Click on Delete
- Type the phrase "Delete" into the field below, then press Delete?.

