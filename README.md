# Udagram Deployment Project

This project is to setup automated build/deployment of the Udagram client/server application through Circleci.

Udagram application has two sub modules, Udagram-api which is the node.js server application that will be hosted on AWS elastic beanstalk and
Udagram-frontend which is an Angular application that will be hosted on AWS S3 as a static web site.

The application can be accessed via: http://udagramfrontendjyx.s3-website.us-east-2.amazonaws.com

![udagram app](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-app.jpg?raw=true)

# Architecture Diagram:

udagram-architecture-graph.jpg is the architecture diagram.

Github URL: https://github.com/jiayanweb/udagram-app

![Architecture Diagram](https://github.com/jiayanweb/udagram-app/blob/main/Diagrams/udagram-architecture-graph.jpg?raw=true)

# Udagram-api Information

- Udagram-api is the backend node application that can be called by the frontend to provide interaction to the postgre databases (user information) hosted 
on AWS RDS and image storage using AWS S3.

   Udagram-api is deployed to and hosted on Amazon AWS Eleastic Beanstalk.

- RDS-Configuration: postgres
	RDS Endpoint: postgres.ckesfyi5szh2.us-east-2.rds.amazonaws.com
	udagram-api-rds-setup-01.jpg and udagram-api-rds-setup-02.jpg
   
 - S3 Image Storage bucket: udagramimagexjy
	S3 Resource Name: arn:aws:s3:::udagramimagexjy
	
	Configuration:
	
   ![Image S3 setup 1](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-image-s3-setup-01.jpg?raw=true)
   ![Image S3 setup 2](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-image-s3-setup-02.jpg?raw=true)
   ![Image S3 setup 3](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-image-s3-setup-03.jpg?raw=true)
   ![Image S3 setup 4](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-image-s3-setup-04.jpg?raw=true)
     
- AWS EBS Environment: Jiayanudagramapi2-env
   AWS EBS Application: Jiayanudagramapi2
   AWS EBS Endpoint: Jiayanudagramapi2-env.eba-xbwfqyk3.us-east-2.elasticbeanstalk.com/api/v0
   
   Configuration:
   
   ![api rds setup 1](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-api-rds-setup-01.jpg?raw=true)
   ![api rds setup 2](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-api-rds-setup-01.jpg?raw=true)
   
- Amazon IAM setup
   User: circleciuser
   Setup: 
	![IAM user setup](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/circleci-user-setup.jpg?raw=true)
   
   
	
# Udagram-frontend Information

- Udagram-frontend is the front end of the udagram application written in Angular and hosted on Amazon S3 as a static web site.

- S3: udagramfrontendjyx
   
   Static Web Site End point: http://udagramfrontendjyx.s3-website.us-east-2.amazonaws.com
   
   Configuration:
   
   ![FrontEnd S3 setup 1](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-frontend-s3-setup-01.jpg?raw=true)
   ![FrontEnd S3 setup 2](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-frontend-s3-setup-02.jpg?raw=true)
   ![FrontEnd S3 setup 3](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-frontend-s3-setup-03.jpg?raw=true)
   ![FrontEnd S3 setup 4](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/udagram-frontend-s3-setup-04.jpg?raw=true)



# CICD Process:

The CICD process for the Udagram application is done throught github and circleci

- Developer(s) commit code changes into github repository main branch.
- Circleci workflow gets triggered and start the deployment process.
- The workflow goes through frontend install, backend install, frontend test, backend test, frontend build and backend build.
- The workflow then deploys the frontend to Amazon S3 and backend to Amazon EBS.
![CICD Diagram](https://github.com/jiayanweb/udagram-app/blob/main/Diagrams/udagram-CICD.jpg?raw=true) 



# Circleci Deployment Setup

- Udagram application's deployment is done via Circleci, which connects with the udagram app github repository.

- Circleci configuration: https://github.com/jiayanweb/udagram-app/blob/main/.circleci/config.yml

- Circleci Project Setting: 
   ![Circleci project setting](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/circleci-project-setting.jpg?raw=true)

- Last successful Circleci Deployment:
   ![Circleci build 1](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/circleci-build-01.jpg?raw=true)
   ![Circleci build 2](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/circleci-build-02.jpg?raw=true)


# Amazon AWS Services Status

   ![S3 Status](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/s3-status.jpg?raw=true)
   ![EBS Status](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/ebs-status.jpg?raw=true)
   ![RDS Status](https://github.com/jiayanweb/udagram-app/blob/main/Screenshots/rds-status.jpg?raw=true)