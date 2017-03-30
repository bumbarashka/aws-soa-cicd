# aws-soa-cicd
All to successfully setup CI/CD for SOA on AWS platform. This solution consists of:
* EC2 instance with Jenkins
## Install and connect to EC2 instance
### [Launch the Amazon EC2 instance](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html#ec2-connect-to-instance-linux) 
* Amazon Linux 64-bit Amazon Machine Image (AMI)
* Choose a security group that will allow SSH access as well as port 80 or 8080 to access your Jenkins dashboard.
* Put your *.pem file to .ssh of user's home directory and set 
```
$ chmod 400 /path/my-key-pair.pem
```
### [Installing the AWS Command Line Interface](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)
1. Installing or updating via pip, a package manager for Python
```
$ pip install --upgrade --user awscli
```
2. Check aws cli version
```
$ aws --version
```
3. Uninstall aws cli 
```
$ pip uninstall awscli
```
### [Create Access Keys](https://aws.amazon.com/ru/developers/access-keys/)
This step is required to access your instance from cli.
```
$ aws configure
```
### [Connecting to the Linux Instance Using SSH ](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)
Get instance id or public DNS name of ec2 instance:
```
$ aws ec2 describe-instances
```
Connect to instance. For Amazon Linux instance use 'ec2-user':
```
$ ssh -i /path/my-key-pair.pem ec2-user@ec2-198-51-100-1.compute-1.amazonaws.com
```
Copy file with scp
```
$ scp -i /path/my-key-pair.pem /path/SampleFile.txt ec2-user@ec2-198-51-100-1.compute-1.amazonaws.com:~
```

## Install Jenkins
TODO


