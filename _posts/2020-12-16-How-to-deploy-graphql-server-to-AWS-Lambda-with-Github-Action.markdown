---
layout: post
title:  "How to deploy graphql server to AWS Lambda with Github Action"
date:   2020-12-16 17:11:34 +0700
categories: tech
---

while working on my personal project, I'm trying to deploy a Graphql server written in TypeScript to AWS Lambda using Github Action, which is Github CI/CD tool. I did it because currently using heroku dyno make the prototype very slow. I guess it's because the server is located in US and I'm using the free account. but I don't really understand much about how to speed up the server instance. 

I'm starting by reading a tutorial in [GraphQL official guideline](https://www.apollographql.com/docs/apollo-server/deployment/lambda/) about how to configure the graphql server to deploy in AWS Lambda. From here, I understand that we need to configure the server a little, at least two part is important
1. using [apollo-server-lambda](https://www.npmjs.com/package/apollo-server-lambda)
2. I'm gonna need another tools, *serverless* to deploy the server

But the 2nd point, I don't really like it because it means I need to deploy it from my computer which means it does not achieve my objective for CI/CD using github action. but at least I need to do the first part. But after reading more tuturial, especially from [DEV](https://dev.to/nobleobioma/deploy-node-js-to-aws-lambda-using-github-actions-5a82), I might not need to do that. 

I develop my Graphql server using expressJS. The Graphql acts as middleware so from the main entry point is still expressJS. so it means it has to be similar with other express JS code. What I need to do however, is to export an handler constant value from my index.ts so that it will be understood by the AWS lambda

First, I'm gonna need to create AWS lambda function




