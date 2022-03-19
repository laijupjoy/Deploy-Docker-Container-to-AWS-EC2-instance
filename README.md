# Deploy-Docker-Container-to-AWS-EC2-instance

Docker is a technology that provides the tools for you to build, run, test, and deploy distributed applications 
that are based on Linux containers, which are formed with the help of Docker Engine.

With dockers, there is no need to pre-allocate the RAM or disk space, it takes RAM and disk space according to the requirement.


This project shows how to deploy docker images in AWS EC2 instance.
.

## Steps to deploy docker images in EC2 instance:

1. Launching EC2 instance.
2. Install Docker on EC2 instance.
3. Transfer web application files from Local machine to AWS EC2 instance using WinSCP.
4. Create a Docker image of web application.

## Step 1-:Launching EC2 instance:

In AWS Console search for EC2 and click on that service, we will redirect to the AWS EC2 page 
as follows and then Click on Launch Instance.

To run EC2 successfully, select an Amazon Machine Image (AMI).
AMI contains all the software configurations (operating system, application server, and applications)
required to launch your instance. In this case, we will pick Amazon Linux AMI.

<p align="center">
  <img src="images\1.png" alt="workflow"/>
</p>

## Step 2-:Connected to EC2 instance:

To install Docker on the EC2 Instance, first make connection to EC2 instance.
Go to the location path where your Key Pair is saved, open terminal and type 
the following command:

```bash
ssh -i keypair.pem ec2-user@<EC2-INSTANCE-PUBLIC-IP-ADDRESS>
```

## Step 3-:Install Docker on EC2 instance:

To install Docker on the EC2 Instance, using the below command:

```bash
sudo yum install -y docker
```
Use this command to start the docker:
```bash
sudo service docker start
```
docker info

If done everything right, the below command will shows info about Docker installation without showing any errors.
```bash
docker info
```

## Step 4-:Transfer web application files from Local machine to AWS EC2 instance using WinSCP:

<p align="center">
  <img src="images\2.png" alt="workflow"/>
</p>

## Step 5-:Create a Docker image of web application:

Now we can buil image of web application.

```bash
docker build -t webapp:v1 .
```

<p align="center">
  <img src="images\3.png" alt="workflow"/>
</p>

<p align="center">
  <img src="images\4.png" alt="workflow"/>
</p>

After build docker image, the below command will shows info about Docker images.

```bash
docker images
```

<p align="center">
  <img src="images\5.png" alt="workflow"/>
</p>


Reference: https://docs.aws.amazon.com/AmazonECS/latest/userguide/docker-basics.html
