

1. [Overview](#schema1)
2. [Container Setup](#schema2)
3. [Creating and Using a DockerHub Repository](#schema3)
4. [Travis](#schema4)
5. [Container Teardown](#schema5)

<hr>
<a name='schema1'></a>



# 1. Overview

This is a very simple, bare-bones NodeJS project created for you to use with Docker.

## Local Setup

**_Note_**: This is only needed if you want to run the app locally. You don't need to install the dependencies or run the server if you are running the code inside a Docker container.

- Install dependencies: `npm install`
- Run server: `node server.js`


<hr>
<a name='schema2'></a>


## 2. Container Setup

- Build image: `docker build -t simple-node .  `
- Run container with image: `docker run {image_id}` where `image_id` can be retrieved by running `docker images` and found under the column `IMAGE ID`
- You can use the `-d` flag to run the container in the background. This will enable you to run other commands in your terminal while the container is running.


<hr>
<a name='schema3'></a>


## 3. Creating and Using a DockerHub Repository
1. In DockerHub, create a new repository and set it to `Public`

2. In your terminal, login to DockerHub

```bash
docker login --username={YOUR USERNAME}
```

3. Tag your local image with the repository name:
```bash
docker tag {LOCAL IMAGE NAME} {USERNAME}/{REPOSITORY NAME}

docker tag simple-node patricarrasco/simple-node
```
4. Push the image to DockerHub
```bash
docker push {TAGGED IMAGE}

docker push patricarrasco/simple-node

```

<hr>
<a name='schema4'></a>


## 4. Travis

In travis-ci.com, select repo.

**Environment Variables with Travis**

Travis provides a way to set environment variables without having them exposed. These values will be used during the Travis build process.

- In your TravisCI dashboard, navigate to a repository
- Navigate to the Settings screen
- Set values in Environment Variables
  -  DOCKER_PASSWORD
  - DOCKER_USERNAME


<hr>
<a name='schema5'></a>


## 5. Container Teardown

- Remove container: `docker kill {container_id}` where `container_id` can be retrieved by running `docker ps` and found under the column `CONTAINER ID`