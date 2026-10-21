# Task 21: Create an IAM Group for Read-Only Access

## Aim
To create an AWS IAM group with read-only permissions, assign a test user to the group, and verify that the user can view AWS resources but cannot modify them.

## Objectives
- Understand group-based access management in AWS IAM.
- Apply read-only permissions using an AWS-managed policy.
- Assign a test user to an IAM group.
- Verify allowed viewing actions and denied modification actions.

## Tools and Technologies
- Amazon Web Services (AWS)
- Identity and Access Management (IAM)
- Amazon EC2
- GitHub

## Implementation

### 1. IAM Group
Used the existing IAM group `veda-readonly-group` for this task.

### 2. Permissions
Attached the AWS-managed `ReadOnlyAccess` policy to the group. The group also has `AmazonEC2ReadOnlyAccess` and the existing customer-managed policy `veda-ec2-readonly-policy`.

### 3. Test User
Verified that `veda-readonly-user` belongs to `veda-readonly-group`.

### 4. Allowed Action Test
Signed in as the test user and opened the EC2 Instances page. The user could view the existing EC2 instance.

### 5. Denied Action Test
Attempted to stop the EC2 instance. AWS denied the `ec2:StopInstances` action because no identity-based policy allowed it. The instance remained running.

## Results
- The read-only IAM group was configured.
- The test user successfully viewed EC2 resources.
- AWS denied the instance-stop operation.
- The existing EC2 instance remained running.

## Security Notes
- Read-only access follows the principle of least privilege.
- Group-based permissions simplify access management for multiple users.
- Permissions should be tested before granting access to production resources.
- Avoid sharing passwords, access keys, secret credentials, or other sensitive information in public repositories.

## Cleanup
The existing IAM group, user, and policies were retained to avoid disrupting other internship tasks. No new EC2 instance was created for this test.

## Conclusion
This task demonstrated how AWS IAM groups can provide read-only access to cloud resources. Testing both viewing and modification actions helped verify that the test user could view EC2 resources while the stop operation was denied.

## Evidence
Screenshots demonstrating the group configuration, test user membership, allowed viewing access, and denied modification action will be included in this repository.
