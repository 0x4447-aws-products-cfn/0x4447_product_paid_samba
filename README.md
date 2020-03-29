# OpenVPN-Server

<img align="left" style="float: left; margin: 0 10px 0 0;" src="https://raw.githubusercontent.com/0x4447/0x4447_product_paid_samba/assets/product.png">

We created this CloudFormation file to allow an easy and automated deployment process of our [custom OpenVPN AMI product](https://aws.amazon.com/marketplace/pp/B0839R5C7Z?ref=_ptnr_social_github) - available in the [AWS Marketplace](https://aws.amazon.com/marketplace/seller-profile?id=80edcebf-11fb-4c36-a3f4-49eb40b518a3?ref=_ptnr_social_github). 

You can find the full documentation of how to use our product here: [documentation.0x4447.com](https://documentation.0x4447.com/products/cloud/aws-marketplace/samba-server.html).

# Feature of the stack

Once deployed the stack will create a EC2 instance automatically for you, with a special alarm to automatically recover if there was a AWS Hardware failure. Meaning the OpenVPN server will always be available. Also by default the Instance have termination protection ON.

**IMPORTANT**: all the unique server configuration is stored in the EFS drive. Meaning if you use the same EFS ID in the UserData section - the server will work exactly how you left it.

# How to deploy

<a target="_blank" href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=zer0x4447-samba&templateURL=https://s3.amazonaws.com/0x4447-drive-cloudformation/samba-server.json">
<img align="left" style="float: left; margin: 0 10px 0 0;" src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>

All you need to do to deploy this stack is click the button to the left and follow the instructions that CloudFormation provides in your AWS Dashboard. Alternatively you can download the CF file from [here](https://s3.amazonaws.com/0x4447-drive-cloudformation/samba-server.json).

# What will deploy?

![samba-server](https://raw.githubusercontent.com/0x4447/0x4447_product_paid_samba/assets/diagram.png)

The stack takes advantage of one EC2 Instance. Other resources are listed bellow.

- 1x CloudWatch Dashboard.
- 2x CloudWatch Alarms.
- 1x SNS Topic.
- 1x IAM Role
- 1x EC2 instance with 0x4447 custom OpenVPN AMI.

# Pricing

Once the stack is deployed you will pay for the AWS resources created in your account, plus you will get charged monthly for the 0x4447 OpenVPN custom AMI, the price willvarry based o the instance type hat you'll select when deploying the stack. Check the [product page](https://aws.amazon.com/marketplace/pp/B07YN9CCV4/) to find out about the pricing options.

# How to generate the CloudFormation file

This repo was build using the [Grapes Frameworks](https://www.npmjs.com/package/@0x4447/grapes). To create a CF file locally, first you need to install the framework:

```
sudo npm install -g @0x4447/grapes
```

Then go inside this repo and run this command

```
grapes -s .
```

This will create a `CloudFormation.json` file in the root dir of the repo.

# The End

If you enjoyed this project, please consider giving it a 🌟. And check out our [0x4447 GitHub account](https://github.com/0x4447), where you'll find additional resources you might find useful or interesting.