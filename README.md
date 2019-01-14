# Docker and Kubernetes the Complete Guide

* **IMPORTANT**: I am taking notes from section 7 to 17. For a complete docker tutorial click [here](https://github.com/danielmapar/DockerTutorial)

## **Section 7**: Continuos Integration and Deployment with AWS

* `docker attach ${containerId}`: This attaches the stdin, stout and sterr from the container to the host machine

## Multi-Step Docker Builds

![multi-build](./images/multibuild.PNG) 

Example: 

```docker
FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html
```
* Running a single container using Elastic Beanstalk
  * Create an environment (Web server environment)
  * Select `Docker` as a platform 
  * ![ebs](./images/ebs.PNG) 

## **Section 8**: Building Multi-Container Application

* Setting up NGINX as a reverse proxy to access 2 different services
  * ![nginx](./images/nginx.PNG) 