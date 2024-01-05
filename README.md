# AWS Ops Exercise - EC2 Autoscaling and SQS
This exercise involves setting up an AWS environment where EC2 instances scale based on SQS queue messages. It includes creating an SQS queue, writing Python scripts for a message producer (desktop application) and a consumer (deployed on EC2 instances), setting up an EC2 Auto Scaling group with the consumer script in its bootstrap process, and testing the scale-out/in mechanism based on the queue's message load. This task tests AWS service integration, Python scripting, and understanding of autoscaling principles.

## Step 1: Create SQS Queue
- Set up an Amazon SQS standard queue.
- Configure necessary permissions for the queue.

## Step 2: Create Consumer and Producer Python Scripts
- **Producer Script**: 
  - Write a script to send JSON messages to the SQS queue.
  - Runs on a desktop environment.
- **Consumer Script**: 
  - Develop a script to consume messages from SQS.
  - Script is included in the EC2 instance bootstrap.

## Step 3: Create Auto Scaling Group with Consumer Script
- Configure an Auto Scaling group for EC2 instances.
- Set scaling policies based on SQS queue message count.
- Add the Consumer script to the EC2 instance user data.

## Step 4: Test Scale-Out/In Process
- Use the Producer script to load messages into the SQS queue.
- Monitor the Auto Scaling group and CloudWatch for scaling actions.
- Observe the scale-in process as the queue's message count decreases.

