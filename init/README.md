# Init Stack

The init stack is intent to be deployed **MANUALLY** into an AWS Account.
Usually we are deploying the stack after a new account created.

The following outputs will be created:
- TemplateBucket (S3 Bucket): Used for cloudformation template packaging
- CloudformationRole (Role): Service Role for giving wide access to Cloudformation during resources creation
- User: API User used to automate the deployment of Cloudformation (AWS profile configured in your local machine)
- CloudformationSecretKey: Secret key used for setting up the aws credentials
- CloudformationAccessKey: Access Key ID used for setting up the aws credentials

[Next Steps](https://github.com/continuousphp/cloudformation#pre-requirements)
