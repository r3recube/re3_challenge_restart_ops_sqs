# AWS Ops Exercise - EC2 Autoscaling and SQS
This exercise involves setting up an AWS environment where EC2 instances scale based on SQS queue messages. It includes creating an SQS queue, writing Python scripts for a message producer (desktop application) and a consumer (deployed on EC2 instances), setting up an EC2 Auto Scaling group with the consumer script in its bootstrap process, and testing the scale-out/in mechanism based on the queue's message load. 

## Requirements
This task tests AWS service integration, Python scripting, and understanding of autoscaling principles.

### Mandatory requirements
Essential tasks that test the core competencies required for the position. These include setting up the AWS infrastructure, writing the basic producer and consumer scripts using python, and configuring auto-scaling based on SQS messages. These tasks assess the candidate's fundamental skills in AWS services, Python scripting, and understanding of cloud architecture.

1) Create a standard Amazon SQS queue
2) Define the SQS Access Policy and Configure IAM roles for SQS send/receive operations.
3) Develop a Python producer script to send JSON messages to SQS [example](#examples-of-json-messages)
4) Create a Python consumer script to process messages from SQS and log on standard output the content
5) Set up an EC2 Auto Scaling group with min of 0 instances and max of 4 instances
6) Define scaling policies based on SQS message count (no message in the queue no instances)
7) Include the consumer script in the EC2 instance bootstrap.
8) Consumer script poll messages from the SQS queue, process them, and then wait for one minute before polling for messages again

#### Examples of JSON Messages
```
{
    "vehicleId": "VH2001",
    "make": "Honda",
    "model": "Civic",
    "year": 2020,
    "color": "Blue",
    "mileage": 15000
}
```

### Optional requirements
Advanced tasks that offer the opportunity to demonstrate additional skills. These include configuring CloudWatch for monitoring and logging, creating a CloudWatch dashboard for better visibility of the infrastructure, and using infrastructure as code tools like CloudFormation or Terraform. These tasks are more complex and test the candidate's proficiency in monitoring, optimization, and modern cloud deployment practices.

1) Install CloudWatch agent on EC2 instances at bootstrap or prepare an AMI with agent onboard
2) Configure Cloudwatch agent to send content of messages to CloudWatch Logs
3) Create a CloudWatch dashboard to monitor SQS metrics
4) Create a CloudWatch dashboard to monitor EC2 metrics

### Bonus requirements
This bonus requirement is aimed at candidates who are comfortable with DevOps practices and more advanced AWS functionalities.

1) Use CloudFormation or Terraform for infrastructure creation.
2) Use Ansible to install and configure Cloudwatch agent
3) Share Cloudwatch dashboard with us

## Test Scale-Out/In Process
- Use the Producer script to load messages into the SQS queue.
- Monitor the Auto Scaling group and CloudWatch for scaling actions.
- Observe the scale-in process as the queue's message count decreases.
- Use the Producer script to send messages (exceeding the scale-out threshold) to the SQS queue.
- Monitor the SQS queue to confirm that messages are being queued.
- Observe the initiation of scale-out actions as the number of messages in the queue increases.
- Ensure that the Consumer script on each EC2 instance process and remove messages from the queue.
- Examine CloudWatch metrics to analyze the scaling pattern and instance metrics during the test.
- Check CloudWatch logs to review the logs sent by the EC2 instances for message content or errors.

## Deliverables
Candidates are required to submit the URL of a Git repository containing all the project components.
The repository should include:
- README.md file with detailed documentation of the setup process, configurations, and test results.
- Source code for the Producer and Consumer Python scripts.
- Scripts, command-line instructions or Screenshoot used for setting up the SQS queue, Auto Scaling group, and EC2 instances.
- Any additional configuration files or scripts used in the project.
- A report file containing the test process and observations, including screenshots, logs, and metrics.

Candidates should ensure that their Git repository is well-organized and includes comprehensive documentation to demonstrate their work effectively. This approach allows for an efficient review process and provides a clear understanding of the candidate's technical abilities and approach to problem-solving.







- Python code of producer script
- Python code of consumer script
- Terraform or Cloudformation Template (if any)
- Autoscaling 