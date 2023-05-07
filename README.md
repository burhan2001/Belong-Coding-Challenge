# Belong-Coding-Challenge

## Deploy the CloudFormation stack

### Using AWS CLI
- Login to your AWS CLI in Sydney region
- Clone this git repository and negivate to the location where the yaml file is saved
- Run this command to deploy the Cloudformation stack

```sh
aws cloudformation create-stack \
  --stack-name belong-code-challenge \
  --template-body file://belong-code-challenge.yaml
```

> Note: You can change the stack-name

Wait for few minutes for the stack creation to be completed.

### Using AWS Portal
- Login to your AWS portal and choose Sydney region
- Create a CloudFormation stack using the yaml file given in this repository
- You can name anything to the stack.

Wait for few minutes for the stack creation to be completed.