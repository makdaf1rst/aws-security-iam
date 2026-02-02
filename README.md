<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** saqibh49@gmail.com  
**Email:** saqibh49@gmail.com

---

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to create IAM users in AWS and guve them certain levels of access. I'm doing this project to learn how to give the right people access to my projects and others just access to the finished product.

### Tools and concepts

Services I used were IAM and EC2. Key concepts I learnt include how to add a user, add user groups, set up a policy and relate it to a specific user or user group and how to test whether a policy's permissions are working correctly on a user's account both the hard way and the easy way.

### Project reflection

This project took me approximately 1 hour. The most challenging part was just naviagting for the first time since it can be tough to find items in large lists and complex dashboards. It was most rewarding to see the policy work on the new user.

---

## Tags

### What I did in this step

In this step, I will create two AWS EC2 instances because that will help increase computing power so more users can use the service at once.

### Understanding tags

Tags are ways of marking an instance and everything in it so it's easy to tell what it's being used for, For example, you don't want to be experimenting on production grade projects, whereas you can try some things in a dev project and not worry as much about breaking something.

### My tag configuration

The tag I’ve used on my EC2 instances is called Env. The value I’ve assigned for my instances are production and development.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy because I want to make sure only the correct people have access to certain instances. For example, I don't want an intern to have access to the production instance, since I don't want them testing things there.

### Understanding IAM policies

IAM Policies are a set of rules that decide who can access what in a certain project.

### The policy I set up

For this project, I’ve set up a policy using JSON

### Policy effect

I’ve created a policy that allows the IAM user to do any action in the development instance except create tags or delete tags

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means: 

Action: A list of actions that are allowed or denied in an instance
Effect: This basically tells us what actions the policy allows or denies
REsource: Tells use what resources within an instance this policy relates to

---

## My JSON Policy

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will create an account alias because that will make it much simpler to log into the AWS account.

### Understanding account aliases

An account alias is is a more user friendly way of accessing an AWS account, Instead of having to remember the account ID to get to the right url, the user can just use the alias in the url instead.

### Setting up my account alias

Creating an account alias took me 10 seconds. Now, my new AWS console sign-in URL is https://nextwork-alias-saqib.signin.aws.amazon.com/console

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will set up an IAM group just for interns and an IAM user for a new intern because I want to give interns access to specific instances and not others

### Understanding user groups

IAM user groups are a way of grouping users with the same permissions together so we don't have to update users individually.

### Attaching policies to user groups

I attached the policy I created to this user group, which means, anyone in this user group will be only be able to do actions in the development instance.

### Understanding IAM users

IAM users are users or computers within AWS that can access an account

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is by email and the 2nd is by downloading and sharing a .csv file.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed some of the items were showing access denied. This was because of the restrictions set up by the policy earlier.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will log into the intern's IAM user's account because I want to make sure the permissions are set up correctly to allow them to access only what I want them to access.

### Testing policy actions

I tested my JSON IAM policy by attempting to make changes to my 2 instances. My policy states I can only make changes to my development instance, so when I tried to touch the production instance, it gave me an error.

### Stopping the production instance

When I tried to stop the production instance I got an error message. This was because of the permissions set in my policy from earlier.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance it stopped just fine because that's allowed in my policy

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to test out my policy using a policy simulator. I'm doing this because shutting down an actual instnance just to test a policy can cause problems for other users using the instance at the same time.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a safe, quick way of testing an IAM user's permissions. It's useful for making sure people have and don't have access to certain things 

### How I used the simulator

I set up a simulation to stop an instance and the results were that the user did not have permission. I had to adjust the specifics of the stopinstance action so it only was trying to stop instances with the tag development and it worked just fine.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-security-iam_069d8a621)

---

---
