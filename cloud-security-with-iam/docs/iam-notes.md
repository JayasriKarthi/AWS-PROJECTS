<section>
  <h2>What I Did</h2>
  <p>
    I created a custom IAM policy that allows users to access only development
    EC2 instances.
  </p>

  <h2>IAM Users and User Groups</h2>

  <h3>IAM User Groups</h3>
  <p>
    IAM user groups help manage permissions for multiple users at once.
  </p>

  <p>
    Instead of assigning policies individually, policies can be attached
    directly to groups.
  </p>

  <h3>IAM Users</h3>
  <p>
    IAM users represent individuals who need access to AWS resources.
  </p>

  <p>
    In this project, I created an IAM user for interns and attached them to
    the development access group.
  </p>

  <h2>Testing IAM Permissions</h2>

  <h3>Logging in as an IAM User</h3>
  <p>
    I logged in using the IAM user credentials to test whether the policy
    worked correctly.
  </p>

  <h3>Production Instance Testing</h3>
  <p>
    When attempting to stop the production EC2 instance, access was denied
    because the policy only allows access to development resources.
  </p>

  <p>
    This demonstrates secure permission boundaries in AWS IAM.
  </p>

  <h3>Development Instance Testing</h3>
  <p>
    The IAM user was able to interact with the development EC2 instance
    because the correct resource tag matched the IAM policy condition.
  </p>
</section>

![alt text](../images/iam-user-credentials.png)