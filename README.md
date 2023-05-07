# Belong Platform Engineering Coding Challenge

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

## Check httpd service

### Using AWS CLI
- Check the output of the CloudFormation stack using this command 

```sh
aws cloudformation describe-stacks --stack-name belong-code-challenge
```

> Note: If you changed the stack-name in previous step then please update it accordingly.

- Come down to the **Outputs** part of the the command output
- Copy the **OutputValue** from **OutputKey** "WebIP"
- Put it in a web browser.
- You should be able to see the 'belong-test.html' as webpage.

### Using AWS Portal
- Go to the **Outputs** tab of the ClouFormation stack.
- Copy the **Value** of **Key** "WebIP"
- Put it in a web browser.
- You should be able to see the 'belong-test.html' as webpage.

## Terminal access to the server
- Because the webserver is placed in a private subnet, direct ssh access not possible to it.
- A Bastion server has been created in public subnet via which ssh access can be made to to the webserver.

- **Follow these steps:**
- In the Stack outputs check the **Value** of **Key** "KeyPairID"
- Go to **AWS Systems Manager** -> **Parameter Store**
- Find the parameter with above KeyPairID and click on it.
- Copy the value of this parameter and save it as .pem file.
- In the Stack outputs check the **Value** of **Key** "BastionEIP"
- Now ssh the the Bastion Server to the above BastionEIP using the .pem file as key file and **ec2-user** as Username.
- To login the webserver, get the private IP of the webserver from the Stack outputs **Value** of **Key** "WebServerIP"
- ssh the "WebServerIP" from inside Bastion server.