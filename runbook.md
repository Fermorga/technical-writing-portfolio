# Cloud Monitoring Runbook: Accessing Amazon CloudWatch

## Purpose
This runbook defines the operational procedure for accessing Amazon CloudWatch via the AWS Management Console to monitor infrastructure health, review performance metrics, and triage active system alarms.

## Audience
This document is intended for Cloud Engineers, Site Reliability Engineers (SRE), and IT Support teams responsible for infrastructure monitoring.

## Prerequisites
* An active AWS Account.
* Valid AWS IAM user credentials or Identity Center single sign-on access.
* Assigned IAM permissions granting read-access to CloudWatch resources (CloudWatchReadOnlyAccess or equivalent custom policy).

## Operating Procedure

### Step 1: Authenticate to the AWS Management Console
1. Navigate to the AWS Sign-In portal.
2. Choose your user type (Root user or IAM user).
3. Input your Account ID, username, password, and complete the Multi-Factor Authentication (MFA) challenge if prompted.

### Step 2: Navigate to the CloudWatch Service
1. Locate the global search bar at the top of the AWS Management Console homepage.
2. Type "CloudWatch" into the search field.
3. Select CloudWatch from the dropdown services list to open the service console dashboard.

### Step 3: Audit System Metrics and Health
Once inside the CloudWatch console, navigate the left-hand menu sidebar to perform the following operations:
* Alarms: Review "All alarms" to check for any active "In alarm" states indicating system failures.
* Metrics: Select "All metrics" to visualize resource utilization patterns (e.g., EC2 CPU Utilization, RDS Memory).
* Logs: Select "Log Groups" to query system applications or infrastructure event streams.

## Verification
Verification is successful when the CloudWatch home dashboard loads without permission errors, displaying active resource metrics and status widgets.

## Troubleshooting

| Issue | Potential Cause | Resolution Steps |
| :--- | :--- | :--- |
| Authentication failure / Access Denied | Invalid credentials or expired session tokens. | Re-verify credentials, reset MFA tokens, or contact your IAM administrator. |
| "Not Authorized" warning on CloudWatch dashboard | Missing explicit IAM read permissions for CloudWatch. | Ensure your IAM user or role has the CloudWatchReadOnlyAccess policy attached. |
| Empty metrics or missing log streams | Target cloud resources are stopped or the CloudWatch agent is misconfigured on the host machine. | Check target instance run-states and verify that the CloudWatch agent daemon is running. |

## Related Documentation
* Amazon CloudWatch User Guide
* AWS Identity and Access Management (IAM) Documentation