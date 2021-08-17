





## Commands CLI
* To run an EC2 instance with oneline command
```shell
aws ec2 run-instances --image-id ami-0164f9b296f8e78cc --instance-type t4g.micro --count 1 --key-name Calvin_Key_Pair --security-group-ids sg-0ad8af9859c84d24d --subnet-id subnet-0983cbe1804161068 --block-device-mappings DeviceName=/dev/sdh,Ebs={VolumeSize=10}  --dry-run
```
* stop instance
```shell
aws ec2 stop-instances --instance-id i-123456
```


Tools:
* AWS Cloud9 : Creates a Development environment
    * Has all apps you can download 

* AWS X-Ray : helps to track all actions. 
    * Will show you how long the rocess takes ime
    * Shows errors etc
    * X-Ray Commands: https://docs.aws.amazon.com/xray/latest/api/API_Operations.html
    * instromentantion for code

* AWS CloudWatch: Monitor performance metrics/ analytic
    * Collects ant tracks metrics
    * Setup alarms
    * Create dashboards
    * Does not tall you one of instances sotting down

* AWS CloudTrail: tells you who, what and why?

* AWS IAM(Identity Access Management)
    * Security of the Cloud = AWS
    * Security in the Cloud = You
    * To see who changed user account? Configure AWS CloudTrail or not.
