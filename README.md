FortiGate Backup Automation
Overview

The FortiGate Backup Automation project introduces a streamlined and feature-rich solution to enhance the process of backing up FortiGate configurations. This solution leverages AWS CloudFormation for seamless deployment, automated daily backups, and prioritizes security through the use of isolated resources.
Key Features
1. CloudFormation Integration

The solution is encapsulated into AWS CloudFormation, ensuring seamless deployment across environments. This integration makes it efficient and easy to manage.
2. Automated Daily Backup

The automation is scheduled to run daily at 2:00 AM UAE time, guaranteeing regular FortiGate configuration backups without manual intervention.
3. Securely Isolated Resources

To prioritize security, the solution utilizes AWS services with private endpoints, ensuring complete isolation from the public internet.
Main Resources Created

    S3 Bucket:
    A dedicated S3 bucket has been established to securely store FortiGate configuration backups.

    Secrets Manager Secret:
    A Secrets Manager secret is in place to securely store the API key essential for FortiGate access.

    Lambda Function:
    A Lambda function is responsible for executing the backup process.

    EventBridge Rule:
    An EventBridge rule ensures the daily trigger at 2:00 AM UAE time for initiating the backup process.

    S3 Gateway Endpoint:
    A VPC Endpoint for S3 has been created, allowing secure and private communication with the S3 service.

    Secrets Manager Interface Endpoint:
    A VPC Endpoint for Secrets Manager ensures secure access to the Secrets Manager service.

Prerequisites

Before deploying the solution, please ensure the following:
VPC Settings:

Confirm that enableDnsHostnames and enableDnsSupport are enabled in the VPC settings.
API Key Setup:

Generate an API key with super_admin rights using the provided CLI command:

bash

config system api-user
    edit "test"
        set api-key ENC blahblah
        set accprofile "super_admin"
        set vdom "root"
    next
end

Deployment

    Clone this repository.
    Deploy the CloudFormation template (cloudformation-template.yml) in your AWS environment.

Source Code

The source code for the FortiGate Backup Automation project can be found in the src directory.

Feel free to contribute, report issues, or suggest improvements. We welcome your feedback!

Happy Automating!
