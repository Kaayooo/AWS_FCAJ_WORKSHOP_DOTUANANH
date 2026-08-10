---
title : "Clean up"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

Congratulations on completing this workshop!

You have now walked through a simplified version of the architecture described in the proposal and worklog, from ingestion to dashboard deployment.

#### Cleanup checklist

1. Delete the S3 buckets you created for raw and curated data.
   - Empty the buckets first if they contain objects.

2. Remove the AWS resources created for the workshop:
   - Lambda functions
   - Step Functions state machines
   - Glue crawlers, jobs, and databases
   - API Gateway APIs and Lambda backends
   - Amplify app and Cognito resources
   - CloudWatch log groups and EventBridge rules

3. Review IAM roles and policies created for the workshop and remove those that are no longer needed.

4. Confirm that no unexpected charges remain in your AWS account.

#### Final note

This cleanup step is important because the workshop is intended to demonstrate the architecture and should not leave behind unused resources in your AWS account.