# Troubleshooting


Problem

While logged in as the IAM user, I received an Access Denied error when trying to stop or manage EC2 instances.

Cause

The IAM policy only allowed access to EC2 instances tagged with:

"Env": "development"

The production instance had a different tag value, so AWS denied access automatically.

Solution

I verified:

The EC2 instance tags
The IAM policy conditions
The attached user group permissions

After checking the tag configuration, I understood why the production instance was restricted.