-include ../.env

region?=us-east-1
role?=arn:aws:iam::$(account_id):role/cloudformation-role
stackName?=continuous-shared-cf-network

ifndef bucket
$(error You must specify bucket parameter)
endif

ifndef role
$(error You must specify role parameter)
endif

ifndef profile
$(error You must specify profile parameter)
endif

package-vpc:
	aws --profile $(profile) --region $(region) \
	 cloudformation package \
		 --template-file vpc.yml \
		 --s3-bucket $(bucket) \
		 --output-template-file vpc-output.yml

deploy-vpc: package-vpc
	aws --profile $(profile) --region $(region) \
	 cloudformation deploy \
		 --template-file vpc-output.yml \
		 --s3-bucket $(bucket) \
		 --capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND \
		 --role-arn $(role) \
		 --stack-name $(stackName) \
		 --parameter-overrides RegionAzs=2 CidrBlockPrefix=192.169 RunNat=true
