# dynmodb_integration_springboot
SPRINGBOOT DYNAMODB 

Create Dynamo DB: create 1st a simple dynamo DB . 
 

Now to access the table from java application we need certain key.

We need to set the  IAM access and need to generate a  key 
1.	Under the IAM we need to 1st create a group and we need to add user to the group and also to that user need to add some policy, then only java application can interact with cloud AWS Dynamo DB.
2.	
 
As we can see there is a group we have to create the spring boot to interact with dynamo DB. When creating group we need to add the policies to the group as we can see I have checked 
AmazonEC2FullAccess 
AdminstratorAccess
Then create group.

 

Now to the above created group we need to add a user 
 
As per above screenshot attached, you can Select the I want  to create a I am User and it will create a new user with password then you can choose auto generate password or your on custom password 

Now click next add the group to this user follow the below screenshot 
 
 
 


We have created a group and attached a user and  now lets add a custom policy to that group . 

Now add the policy custom policy for the new policy at JSON postion adding custom policy for Dynamodba and sns

{
	"Version": "2012-10-17",
	"Statement": [
		{
		    "Effect":"Allow",
			"Action": ["dynamodb:PutItem"],
			"Resource": ["*"]
		},
			{
		    "Effect":"Allow",
			"Action": ["sns:Publish"],
			"Resource": ["*"]
		}
	]
}
 

As we can notice at below screenshot the two policies  has added simply we need to add the new policy name and create the policy 

 

 

Now lets attach the policy to the group we need to check the policy radio button and  click on action 
 

 

Now we are done with the configuration lets go to the Intellij and create springboot application 




