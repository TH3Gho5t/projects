<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** mgardner  
**Email:** cliches_tinfoil.4r@icloud.com

---

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use IAM and user groups to control access to EC2s. I'm doing this project to learn how to grant and deny secure access to resources in AWS. 

### Tools and concepts

Services I used were IAM, user groups, account aliases, and the policy simulator tool.  Key concepts I learnt include its much cleaner to create a group, give that group a set of permissions then add users to that group as needed.

### Project reflection

This project took me approximately an hour, give or take... The most challenging part was not the project but making time to complete the project.   It was most rewarding to actually see the permissions in action. 

---

## Tags

### What I did in this step

In this step, I will create and launch 2 EC2 instances to increase Nextworks computing power, because the company is expecting increased traffic to the website. 

### Understanding tags

Tags are like labels you can attach to AWS resources to help with organization.  They are helpful for identifying all resources with the same tag at once.

### My tag configuration

The tag I’ve used on my EC2 instances is called Env for environment.  The value I’ve assigned for my instances are development and production.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy that gives access to the development instance,  because the intern needs access to only one instance, in this case development and not th production instance.

### Understanding IAM policies

IAM Policies are rules for who can do what with your AWS resources.  They manage the access level that users and services have to your resources.

### The policy I set up

For this project, I’ve set up a policy using JSON.  But you could also set up policies using the visual editor.

### Policy effect

I’ve created a policy that allowed all actions within the ec2  resource tagged Env-development. 

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means... Effect means whether the policy allows or denies, with denial taking priority.  Action is a list of actions that the policy allows or denies.  Resource is which resources does this policy apply to.

---

## My JSON Policy

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will simplify user login by creating an AWS account alias because this makes logging in a little more user friendly wirhout having to use the account ID which is usually a mix of digits.

### Understanding account aliases

An account alias is a friendly name you can use instead of  your account ID to sign into the AWS console.

### Setting up my account alias

Creating an account alias took me less than a minute... Now, my new AWS console sign-in URL is https://nextwork-alias-marcusg.signin.aws.amazon.com/console


![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will set up a dedicated IAM group and a dedicated IAM user so they have a way to log in and to manage all intern permissions from one place. 

### Understanding user groups

IAM user groups are the collections/folders of users for easier user managment.

### Attaching policies to user groups

I attached the policy I created to this user group, which means we are granting them the permissions associated with that group.

### Understanding IAM users

IAM users are people or services that need access to your AWS resources.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is through email sign in instructions and the second would be by downloading the .csv file

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed that some of the dashboard panels were showing access denied. This was because AWS was treating the log in as a new user starting from 0.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will log in to AWS using the intern's IAM user and test the intern's IAM user's access.  Because that way we can make sure they have the right access to our development instance and not the production instance.

### Testing policy actions

I tested my JSON IAM policy by attempting to stop an instance that was not allowed and by attempting to stop an instance that was allowed. 

### Stopping the production instance

When I tried to stop the production instance a large red error message popped up and it did not allow me to stop the instance.  This was because the signed in user is not authorized to make those kinds of changes to the account.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance the policy allowed the action and the instance was stopped.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to test a special IAM tool called the Policy Simumlator.  I'm doing this because shutting down an instance to test policy could get disruptive for other engineers and users had this been a real operation.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a faster and less disruptful way to test policies. It's useful for when you need to test or check a policy and want to do it in a controlled environment.

### How I used the simulator

I set up a simulation for the development instance.  The results were denied initially.  I had to adjust the resource to include specifically the dev environment as that is only one that allows this user to make changes such as stopping the instance.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-security-iam_069d8a621)

---

---
