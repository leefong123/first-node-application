# first-node-application
My first node application 


# Step by step guide of creating an image until deployed to AWS ECR
1. Retrieve an authentication token and authenticate your Docker client to your registy

Use the AWS CLI:

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com

Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.

2. Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built:

docker build -t nodejs-app-lfchin-17apr2024 .

3. After the build completes, tag your image so you can push the image to this repository:

docker tag nodejs-app-lfchin-17apr2024:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/nodejs-app-lfchin-17apr2024:latest

4. Run the following command to push this image to your newly created AWS repository:

docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/nodejs-app-lfchin-17apr2024:latest
