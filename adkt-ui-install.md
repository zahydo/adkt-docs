---
title: Installation
description: How to install ADKT UI on your company?.
layout: libdoc/page

#LibDoc specific below
category: UI
order: 70
---
* 
{:toc}

## Installation

### Run a Docker Container with a custom environment:

After having installed the backend ([README](adkt-install.md)) and having the environment variables for the Frontend follow the next steps: 

Configure a `setup.env` file with the env variables:
```env
NEXT_PUBLIC_AWS_PROJECT_REGION="us-east-1"
NEXT_PUBLIC_AWS_COGNITO_IDENTITY_POOL_ID="us-east-1:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxx"
NEXT_PUBLIC_AWS_COGNITO_REGION="us-east-1"
NEXT_PUBLIC_AWS_USER_POOLS_ID="us-east-1_xxxxxxxx"
NEXT_PUBLIC_AWS_USER_POOLS_WEB_CLIENT_ID="xxxxxxxxxxxxxxxxxxx"
NEXT_PUBLIC_AWS_APPSYNC_GRAPHQL_ENDPOINT="https://xxxxxxxxxxxx.appsync-api.us-east-1.amazonaws.com/graphql"
NEXT_PUBLIC_AWS_APPSYNC_REGION="us-east-1"
NEXT_PUBLIC_AWS_APPSYNC_AUTHENTICATION_TYPE="API_KEY"
NEXT_PUBLIC_AWS_APPSYNC_API_KEY="xxx-xxxxxxxxxxxxxxxxx"
```

`docker run -p 3000:3000 --rm --name adkt_web_container -d --env-file setup.env sahydo/adkt_web`

Go to the browser: [localhost:3000](http://localhost:3000)

### Stop the container

`docker stop adkt_web_container`


## Features

- Design Decisions management
- Quality Attributes management
- Internationalization
- Theme Switch
- Authentication