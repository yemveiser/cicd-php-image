# cicd-php-image
This is a github action orkflow to automate the CD of a PHP Docker Image

STEPS:
1. Create the dockerfile for the application
2. create a github repo and configure ssh authentication to link the github repo to the IDE Tool.
3. use github action to automate the build creation of the docker file wheneever there is a change in the code.
4. create ECR on AWS and configure IAM programmatic access.
5. connect the code server to access ECR through the IAM user created.
6. configure the ECR push commands on the code server to connect to ECR.
7. find push command from ECR below.
8.``Use the following steps to authenticate and push an image to your repository. For additional registry authentication methods, including the Amazon ECR credential helper, see Registry Authentication .
Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:

aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/x4t7e1f4
Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.
Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built:

docker build -t 002891/continous_php_image .
After the build completes, tag your image so you can push the image to this repository:

docker tag 002891/continous_php_image:latest public.ecr.aws/x4t7e1f4/002891/continous_php_image:latest
Run the following command to push this image to your newly created AWS repository:

docker push public.ecr.aws/x4t7e1f4/002891/continous_php_image:latest `` 
