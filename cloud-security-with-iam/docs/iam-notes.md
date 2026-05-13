# IAM Notes

What I Did

I created a custom IAM policy that allows users to access only development EC2 instances.

AM Users and User Groups
IAM User Groups

IAM user groups help manage permissions for multiple users at once.

Instead of assigning policies individually, policies can be attached directly to groups.

IAM Users

IAM users represent individuals who need access to AWS resources.

In this project, I created an IAM user for interns and attached them to the development access group.

Testing IAM Permissions
Logging in as an IAM User

I logged in using the IAM user credentials to test whether the policy worked correctly.

Production Instance Testing

When attempting to stop the production EC2 instance, access was denied because the policy only allows access to development resources.

This demonstrates secure permission boundaries in AWS IAM.

Development Instance Testing

The IAM user was able to interact with the development EC2 instance because the correct resource tag matched the IAM policy condition.
