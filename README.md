# Belong-Coding-Challenge

## Deploy the CloudFormation stack

### Using AWS CLI
Login to your AWS CLI in Sydney region
Clone this git repository and negivate to the location where the yaml file is saved.
run this command to deploy the Cloudformation stack

aws cloudformation create-stack \
  --stack-name belong-code-challenge \
  --template-body file://belong-code-challenge.yaml

Note: You can change the stack-name

Wait for few minutes for the stack creation to be complete
