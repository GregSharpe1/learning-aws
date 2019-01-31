# Identity and Access Management 101

IAM allows you manage users and their level of access to the AWS platform

## What does IAM offer?

* Centralised control of your AWS account
* Shared access to your AWS account
* Granular permission
* Identity Federation (facebook, google)
* Multi-factor authentication
* Provide temporary access when/where needed
* Allows you to set up your own password rotation policy
* Integrates with other AWS services

## Four key terms of IAM

### Users

End users, such as people or employees

### Groups

A collection of users. Each user within the group will inherit the permissions of the group

### Policies

Policies are made up of documents, called Policy documents. These are typical written in JSON and they grant/revoke access to certain services to which a user/group/role can do

### Roles

You create roles and then assign them to AWS resources

## Exam Tips

* **IAM is universal**. It does not apply to just regions at this time.
* The "**root account**" is simply the account created when first setup your AWS account. Complete admin access.
* New users have **NO** permissions when first created.
* New users are assigned **Access Key ID** & **Secret Access keys** when first created
* **Cannot** use access keys to log into the console
* Only get to view the secret access key and password **ONCE**
* **Always** setup MFA on your root account!
* Your can create and customise your own password rotation policies.

## Billing

### Billing can be setup from within the Cloud watch services (**ONLY** setup within N.Virgina) to reduce un-wanted expenses
