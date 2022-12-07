# Hosting a Full-Stack Application on AWS

[![CircleCI](https://circleci.com/gh/circleci/circleci-docs.svg?style=svg)](https://app.circleci.com/pipelines/github/Mohamed-Eldakak/AWS-Full-Stack-Application/39/workflows/c5984d12-8d64-4d8e-a6d3-f6989cd4ae55)

### **Udagram is a full stack web application hosted on Amazon Web Services and is the final project under Udacity's Full Stack JavaScript Developer Nanodegree Program.**

-----
# Application is Hosted [Live](http://eldakak-bucket.s3-website-us-east-1.amazonaws.com)
----
# Udacity Review
![deploy review](https://user-images.githubusercontent.com/106033884/206010636-ddfec0d3-1047-4a32-bc17-7b5186d85ffe.jpg)

----
# Amazon Web Services

### AWS Simple Storage Service (S3)

- s3 image

![S3 Bucket](https://user-images.githubusercontent.com/106033884/205687708-c940db42-913f-4490-b7c9-c9317ccea15c.jpg)

### AWS Elastic Beanstalk (EB)

- Health

![eb OK](https://user-images.githubusercontent.com/106033884/205687967-89bd3656-393f-4496-ae9e-d2140aa5a4cf.jpg)


- Elastic Beanstalk configuration

![eb running](https://user-images.githubusercontent.com/106033884/205688017-bc5404e7-e7c2-45fb-8738-c9327e699465.jpg)

### AWS Relational Database Service (RDS)

![RDS database](https://user-images.githubusercontent.com/106033884/205688357-c7f65b40-3110-4183-87e7-28dd978e837b.jpg)

---

## CircleCI

`This full stack web application is deployed with a CircleCI continuous integration pipeline.`

**Pipeline Highlights**:

1. Able to run install and build for both backend and front-end applications
2. Able to deploy for both backend and front-end applications

![circleci Status](https://user-images.githubusercontent.com/106033884/205688697-d01cc533-9275-4360-8732-1058a8f91687.jpg)

- screenshot of the CricleCi Enviroment Variables

![circleci Env Variables](https://user-images.githubusercontent.com/106033884/205688834-50cbf384-38fd-462e-a729-70cfa20b5738.jpg)


------------------------------------------
## Project Setup
1. create .env file in udagram/udagram-api
```bash
    # fill the environment variables to run locally
    POSTGRES_HOST=""
    DB_PORT=5432
    PORT=3000
    POSTGRES_PASSWORD="password"
    POSTGRES_USERNAME ="postgres"
    RDS_DIALECT="postgres"
    POSTGRES_DB="postgres"
    AWS_REGION=""
    AWS_PROFILE=""
    AWS_BUCKET=""
    URL="http://localhost"
    AWS_ACCESS_KEY_ID=""
    AWS_SECRET_ACCESS_KEY=""
    JWT_SECRET="your-secret-token"
```
```bash
    # install backend dependencies
    cd udagram/udagram-api
    npm install
    # start backend for development
    npm run dev
    # build backend for production
    npm run build
    # start backend build file
    node ./www/server.js
    # clean www directory
    npm run clean
```

2. start frontend `NOTE:` make sure you change files in src/environments folder change apiHost for environment.ts to `e.g` http://localhost:3000/api/v0 so you can run it locally!
```bash
  # install backend dependencies
    cd udagram/udagram-frontend
    npm install
    # start frontend
    npm run start
    # build frontend for production
    npm run build
    # start linting frontend
    npm run lint
    # testing
    npm run test
    # end to end testing
    npm run e2e
```
## Pipeline process
in `.circleci` folder `config.yml`:
1. orbs needed for this pipeline:
   - node
   - aws cli
   - elastic beanstalk cli
2. Secondly:
   1. install node version 14.15
   2. Then install frontend dependencies
   3. Install backend/api dependencies
   4. Linting frontend before build
   5. build frontend
   6. build backend/api
3. Finally:
    1. deploy backend
    2. deploy frontend

### Pipeline (CircleCI) Workflow
1. Finish all build jobs in config.yml
2. Start deploying front-end to S3 and backend to Elastic Beanstalk

## Architecture Diagrams

### AWS

![AWS-diagram](https://user-images.githubusercontent.com/106033884/205690240-4b54d6d1-39db-46c7-ab1a-cfb1a1441b16.jpeg)


### CircleCI

![CircleCI-diagram](https://user-images.githubusercontent.com/106033884/205690295-b2944675-0813-409f-bae7-caeb967313f0.jpeg)


--------
## Documentation

Documentation about the architecture, infrastructure description, app dependencies, and the pipeline process are found inside the [docs](https://github.com/Mohamed-Eldakak/AWS-Full-Stack-Application/tree/main/docs) folder.

------

## Author

The code was written by **Mohamed Eldakak** ([@mohamed-eldakak](https://github.com/mohamed-eldakak)) , for the project by Udacity.


