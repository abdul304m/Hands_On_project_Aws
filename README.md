# Hands_On_project_Aws
in this project, we showcase how you can successfully build IAM user management for Zappy e-Bank, including scalable access setup for backend developers (like John) and data analysts (like Mary). Below is a step-by-step process:

## Log into AWS console
1. search for IAM and click on it
![searching-IAM](./New-pic-14/1,searching-IAM.png).

## Create IAM Group with Attach policies .
This allows you to manage permissionfor roles, and simply add user to the right group.

1. Create Group for BackendDevGroup.
- Go to your IAM Dashboard, click on userGroup and create group
![create-group](./New-pic-14/2.Create-group-for-backend.png)

- Name it BackendDevGroup
![name-the-group](./New-pic-14/3.Nmae-the-group.png).

2. Follow the same proceedure to create anaother group for DataAnalystGroup.

## Create Policy for BackendGroup.

1. In the IAM console , click on policies and create policy.
![create-policy-for-backend](./New-pic-14/6.Create-policy-for-dev.png).

2. In the select a service section, search for EC2. And for simplicity select the "All EC2 Action" 
![selecting-EC2](./New-pic-14/7.SETTING-POLICY.png).

3. Also, select "ALL" In the resources section, and click next.
![Setting-resources](./New-pic-14/8.Setting-resources.png).

4. Give it a name "Developers". And click on create policy.
![Naming-the-policy](./New-pic-14/9.naming-the-policy.png).

5. Checking the policy. when you search for developers , you see that you are the one managing The policies of the group unlike the others which are being managed by the AWS,
![CHECKING-POLICY](./New-pic-14/10.checking-policy.png).

## Create policy For the DataAanalystGroup
1. Repeat the same process abaove for DataAnalyst, but instead of EC2, search for S3.Also named the policy Analyst instead of Developers.
![creating-policy-for-Data](./New-pic-14/11.Creating-Data-policy.png).

## Attach policy Created to The BackendDevGroups
This will allow users in the BackendDevGroup to have access to EC2 instances.
1. Go to user group and select BackendDevGroup.
![assign-permission](./New-pic-14/13.permission-for-Dev.png).

2. Move to permission and click on add permission and select attach policies.
![Adding-permission](./New-pic-14/14.Adding-permission.png).

3. In the search cullumn, search for developers, select it and click attach policy.
![search-for-dev](./New-pic-14/15.search-and-select-dev.png).

4. you have successfully created a group and attach permission policies to any user in the group.
![](./New-pic-14/16.press-attach-policy.png).

## Creating IAM user and Assign to the Group
Lets create users John and mary.

A. Create user john and Add to BackendDevGroup.
1. Go to user and click on add user
![creating-user](./New-pic-14/17.create-user.png).

2. provide name for the user "john.backend" in this case and select access type 'Aws management console. set a custom password.
![naming-the-user](./New-pic-14/18.Naming-user.png).

3. On permission screen: choose add user to the group and select BackendDevGroup.
![Add-user-to-the-group](./New-pic-14/19.Add-user-to-group.png).

click create. you successfully create a user and add the user to the group.

4. Repeat the same proceedure to create user mary. But mary is Data analyst, so she should be added to the DataanalystGroup.

# Testing and Validation.

## Testing John Access; 
1. log in as john into the Aws management console to ensure he has the correct access.
![testing-john-access](./New-pic-14/21.Testing-john-acc.png).

2. in the Dashboard search bar, search for EC2 .
![searching-EC2](./New-pic-14/22.checking-EC2.png)

3. check if john can start and stop instance.
![viewing-instance](./New-pic-14/23.VIEWING-INSTANCE.png).

4. Launch instance
![launch-instance](./New-pic-14/24.Launch-instance.png).

## Testing mary's Access
1. log in as mery but in the dashboard search bar search for s3.
![testin-mary](./New-pic-14/25.Testing-mary-acc.png).

2. perform s3 action to create s3 bucket. click create bucket and provide a name .
![naming-bucket](./New-pic-14/26.Naming-buket.png).

3 click create bucket
![create-bucket](./New-pic-14/27.creating-bucket-for-mary.png).

## checking Role for both users
1. in the mary search bar , search for Ec2, you see that maty is not authorize to perform such operation.
![checking-role](./New-pic-14/28.mary-not-autorize.png).

2. Go to john dashboard and search for s3 or create a bucket , you see that john is not authorize to perform such acttion.
![checking-role-for-john](./New-pic-14/29.john-denied-access.png).

# Creating Multi-Factor Authentication(MFA).

## Setting up MFA For John;
1. click on user and click on john.
![creating-MFA-for-john](./New-pic-14/30.creating-MFA-FOR-john.png).

2. click on enable MFA .
![enable-MFA](./New-pic-14/31.Enable-MFA.png).

3. Enter a device name for john MFA and select Authentication App.
![naming-MFA](./New-pic-14/32.Name-MFA.png).
Note; you need to install authenticator app on your mobile device.

4. click on next and open the authenticator app on your mobile device to scan the  QR Code. Then you can fill in the two consecutive .
![scan-the-code](./New-pic-14/33.SCAN-CODE.png).

5. By completing these steps MFA will be enable for john.

## setting MFA for mary.
1. Repeat the same step for mary.
