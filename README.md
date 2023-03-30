## Cloud 9 Bootstrapping 

### Summary
This Cloudformation Deployment shows how to deploy an AWS Cloud9 Environment for yourself or team members and run an automated bootstrap so you can install software components needed on the fly. 
This is usefull for workshops, unified deployments, etc. 

you may use the template directly or leverage the bash shell script for deployment
### Parameters

There are a few parameters you might want to adjust. 

| Parameter Name | Description | 
| ------------- | ------------- | 
| C9InstanceType |  Cloud9 EC2 instance type |
| C9EnvType | Environment Type. For yourself or to be deployed to a team member 3rd person by you? | 
| OwnerArn | if you selected "3rd person" when choosing C9EnvType please add the OwnerARN of the User or Role |
| C9InstanceVolumeSize | The size of the System Volume for the Cloud9 instance |

### Some tech Details
This deployment uses Cloudformation to deploy Cloud9 
It does include a Custom:Resource to pull the EC2 InstanceID from the Cloud9 Instance and applies an InstanceRole and Profile to the Cloud9 Instance. 
Also it creates a AWS Systems Manager Automation Document and Job which does the bootstrapping once the instance booted up. 
After the bootstrap process the instance gets a one-time reboot. 

Please plan around 15min to a finished, ready to use Cloud9 Instance/Environment

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.