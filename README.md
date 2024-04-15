# cost-optimization-aws
Deletes unused resources to save cost

This Lambda function carries out the following tasks:

Initializes AWS clients for EC2 and snapshot services.

Gathers a list of all EC2 instances.

Retrieves a list of all snapshots owned by the AWS account.

Iterates over each snapshot and verifies if it is associated with any active EC2 instances.

Deletes the snapshot if it is not linked to any active EC2 instance.

Records each snapshot deletion in the logs.

Concludes by signaling a success message, confirming the completion of snapshot cleanup.

Ensure that the Lambda function holds the essential IAM permissions to describe EC2 instances and snapshots, as well as permissions to delete snapshots. Furthermore, schedule the Lambda function to execute at regular intervals using CloudWatch Events or another suitable scheduling mechanism.
