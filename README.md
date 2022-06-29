<!--
title: 'Serverless Framework Node Express API service backed by DynamoDB on AWS'
description: 'This template demonstrates how to develop and deploy a simple Node Express API service backed by DynamoDB running on AWS Lambda using the traditional Serverless Framework.'
layout: Doc
framework: v3
platform: AWS
language: nodeJS
priority: 1
authorLink: 'https://github.com/serverless'
authorName: 'Serverless, inc.'
authorAvatar: 'https://avatars1.githubusercontent.com/u/13742415?s=200&v=4'
-->

# Serverless Framework Node Express API on AWS

This template demonstrates how to develop and deploy a simple Node Express API service, backed by DynamoDB database, running on AWS Lambda using the traditional Serverless Framework.


## Anatomy of the template

This template configures a single function, `api`, which is responsible for handling all incoming requests thanks to the `httpApi` event. To learn more about `httpApi` event configuration options, please refer to [httpApi event docs](https://www.serverless.com/framework/docs/providers/aws/events/http-api/). As the event is configured in a way to accept all incoming requests, `express` framework is responsible for routing and handling requests internally. Implementation takes advantage of `serverless-http` package, which allows you to wrap existing `express` applications. To learn more about `serverless-http`, please refer to corresponding [GitHub repository](https://github.com/dougmoscrop/serverless-http). Additionally, it also handles provisioning of a DynamoDB database that is used for storing data about users. The `express` application exposes two endpoints, `POST /users` and `GET /user/{userId}`, which allow to create and retrieve users.

## Usage

### Deployment

Install dependencies with:

```
npm install
```

and then deploy with:

```
serverless deploy
```

After running deploy, you should see output similar to:

```bash
Deploying aws-node-express-dynamodb-api-project to stage dev (us-east-1)

✔ Service deployed to stack aws-node-express-dynamodb-api-project-dev (196s)

endpoint: ANY - https://xxxxxxxxxx.execute-api.us-east-1.amazonaws.com
functions:
  api: aws-node-express-dynamodb-api-project-dev-api (766 kB)
```
