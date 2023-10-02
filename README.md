# AWS Version Control

## Implementation of Git Repository for applications and Infrastructure code using AWS CodeCommit and developing a Proof-of-Concept process of commit, push and revert code changes. 



## Step 1:  Create 2 Git Repos on AWS CodeCommit and connect on AWS Cloud9

Human-gov-application

Human-gov-infrastructure

Configure the AWS CLI credentials helper on your AWS Cloud9 EC2 development environment.


## Config for DevOps Engineer

>git config --global user.name "Jean Rodrigues - DevOps Engineer"

>git config --global user.email jrodrigues@humangov.com


>git config --global credential.helper '!aws codecommit credential-helper $@'

>git config --global credential.UseHttpPath true

In the terminal run the git clone command, specify the HTTPS clone URL of the repository you want to clone. Clone the repo named human-gov-infrastruture. 

>git clone <https://git-codecommit.us-east-1.amazonaws.com/v1/repos/human-gov-infrastructure

>git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/human-gov-application


## Step 2: Using AWS Cloud9, perform poc process of commit, push and revert code changes.

A). As Software Dev 1

Create and configure a Cloud9 environment to simulate Software dev working environment.

>git config --global user.name "Software Developer 1"

>git config --global user.email dev1@humangov.com

>git config --global credential.helper '!aws codecommit credential-helper $@'

>git config --global credential.UseHttpPath true

Clone the Code Commit repo human-gov application

>git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/human-gov-application

Create a file index.html inside of the repo.

><!DOCTYPE html>
><html>
><head>
><title>My Website</title>
></head>
><body>
><header>
><h1>Welcome to HumanGov!</h1>
><nav>
><ul>
><li><a href="#">Home</a></li>
><li><a href="#">About</a></li>
><li><a href="#">Contact</a></li>
></ul>
></nav>
></header>
><main>
><p>This is a PoC for HumanGov Git Repository.</p>
></main>
><footer>
><p>© My Website. All rights reserved.</p>
></footer>
></body>
></html>

Commit and push the first commit.

>git add .

>git commit -m "first commit"

>git push -u origin master

Create a typo in the Header, commit and push the changes.

B). As Software Dev 2

Create and configure a Cloud9 environment to simulate Software Dev 2 working environment.

>git config --global user.name "Software Developer 2"

>git config --global user.email dev2@humangov.com


>git config --global credential.helper '!aws codecommit credential-helper $@'

>git config --global credential.UseHttpPath true


Clone the Code Commit repo human-gov-application

>git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/human-gov-application

Revert the last commit.

>git log

>git revert <hash>

Change the Header to H2

Commit the change.

>git add .

>git commit -m "fixed header size"

Push changes to the remote repository

>git status

>git push -u origin master
