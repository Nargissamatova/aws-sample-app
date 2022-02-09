# AWSSampleApp

# aws_code_deploy
## Steps for AWS Sample App
 1.  **Create IAM Roles - CodeDeploy & EC2CodeDeploy**
 1.  **Create EC2 instance with the following software packages should install**<br/>
 1.  **Choose AMI: Amazon Linux 2**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/AMI.png)<br/>
 1.  **Choose AMI role as EC2CodeDeploy**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/ConfigureInstance.png)<br/>
 1.  **Choose User Data: for installing required packages.**<br/>
     ```#!/bin/bash<br/>
     sudo yum -y update<br/>
     sudo yum -y install ruby<br/>
     sudo yum -y install wget<br/>
     cd /home/ec2-user<br/>
     wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install<br/>
     sudo chmod +x ./install<br/>
     sudo ./install auto<br/>
     sudo yum install -y python-pip<br/>
     sudo pip install awscli<br/>
     ```
     
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/UserData.png)<br/>
 1.  **Security groups: which enable port SSH port 22 and HTTP 80 for application**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/configureSecutiryGroup.png)<br/>     
 1.  **Add tags to your EC2 instance**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/addTags.png)<br/>
 1.  **Launch instance**<br/>
 1.  **Goto CodeDeploy Create Application**<br/>
 1.  **Create a DeploymentGroup**<br/>
 1.  **Go to CodePipeline and create a new pipeline**<br/>
 1.  **Choose the source provider as CodeCommit or Github**<br/>
 1.  **Add source, build, deploy stages**<br/>
 1.  **Try all the relevant AWS tools e.g. Cloud9, CodeCommit, CodeBuild, CodeDeploy and CodePipeline 
 (No worries if some of these do not work instantly we can always try later :)**<br/>
 1.  **You can verify if codedeploy is running from this command in EC2 instance**
     ```sudo service codedeploy-agent status```

**References**:
 https://docs.aws.amazon.com/codedeploy/latest/userguide/instances-ec2-create.html <br/>
 https://docs.aws.amazon.com/codedeploy/latest/userguide/getting-started-create-iam-instance-profile.html#getting-started-create-iam-instance-profile-console
 
 
 
