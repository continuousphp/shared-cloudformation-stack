# Init Stack

The init stack is intent to be deployed **MANUALLY** into an AWS Account.
Usually we are deploying the stack after a new account created.

The Following resources will be created:
- S3 Bucket: Used for cloudformation template packaging
- Role: Service Role for giving wide access to Cloudformation during resources creation
- User: API User used to automate the deployment of Cloudformation

