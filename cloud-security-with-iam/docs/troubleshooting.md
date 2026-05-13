# Troubleshooting
![alt text](../images/troubleshoot2.png)


![alt text](../images/troubleshoot.png)

<section>
  <h2>Problem</h2>
  <p>
    While logged in as the IAM user, I received an <strong>Access Denied</strong> error
    when trying to stop or manage EC2 instances.
  </p>

  <h2>Cause</h2>
  <p>
    The IAM policy only allowed access to EC2 instances tagged with:
  </p>

  <pre><code>"Env": "development"</code></pre>

  <p>
    The production instance had a different tag value, so AWS automatically
    denied access.
  </p>

  <h2>Solution</h2>
  <p>I verified the following:</p>

  <ul>
    <li>The EC2 instance tags</li>
    <li>The IAM policy conditions</li>
    <li>The attached user group permissions</li>
  </ul>

  <p>
    After checking the tag configuration, I understood why the production
    instance was restricted.
  </p>
</section>

