1. Create EC2 instace (ubuntu) on AWS
2. ssh into it
3. sudo apt update -y
4. sudo apt install docker.io -y
5. sudo systemctl docker status
6. sudo run hello-world    
    --throw error
7. Add ubuntu user to Docker usergroup
    sudo usermod -aG docker ubuntu.  [usermod command is adding ubuntu user to -aG docker group]
8. Logout and login back


## Create the first docker file

Clone this repository and move to example folder
```
git clone https://github.com/parkarneha39/docker-learning.git
cd  examples
```
Login to Docker [Create an account with https://hub.docker.com/]
docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: parkarneha39
Password:
WARNING! Your password will be stored unencrypted in /home/ubuntu/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
Build your first Docker Image
You need to change the username accoringly in the below command

docker build -t parkarneha39/my-first-docker-image:latest .
Output of the above command
```
   Sending build context to Docker daemon  3.072kB
Step 1/6 : FROM ubuntu:latest
latest: Pulling from library/ubuntu
01d7766a2e4a: Pulling fs layer
01d7766a2e4a: Verifying Checksum
01d7766a2e4a: Download complete
01d7766a2e4a: Pull complete
Digest: sha256:d1e2e92c075e5ca139d51a140fff46f84315c0fdce203eab2807c7e495eff4f9
Status: Downloaded newer image for ubuntu:latest
 ---> bbdabce66f1b
Step 2/6 : WORKDIR /app
 ---> Running in 17ee8603a540
 ---> Removed intermediate container 17ee8603a540
 ---> 71046583b4a5
Step 3/6 : COPY . /app
 ---> c26e4ec9ee24
Step 4/6 : RUN apt-get update && apt-get install -y python3 python3-pip
 ---> Running in 3c7415b7142a
Step 5/6 : ENV NAME World
 ---> Running in 547395e70c49
 ---> Removed intermediate container 547395e70c49
 ---> 3c0b878f913e
Step 6/6 : CMD ["python3", "app.py"]
 ---> Running in 0a61d95afc72
 ---> Removed intermediate container 0a61d95afc72
 ---> cab6c445e415
Successfully built cab6c445e415
Successfully tagged parkarneha39/my-first-docker-image:latest
```
Verify Docker Image is created

docker images

Output
```
REPOSITORY                           TAG       IMAGE ID       CREATED         SIZE
parkarneha39/my-first-docker-image   latest    cab6c445e415   2 minutes ago   561MB
ubuntu                               latest    bbdabce66f1b   2 weeks ago     78.1MB
hello-world                          latest    1b44b5a3e06a   6 months ago    10.1kB
```
Run your First Docker Container
docker run -it parkarneha39/my-first-docker-image

Output

Hello World

Push the Image to DockerHub and share it with the world
docker push parkarneha39/my-first-docker-image

Output
```
Using default tag: latest
The push refers to repository [docker.io/parkarneha39/my-first-docker-image]
38f1cc6f4ed4: Pushed 
ee5c88ccc592: Pushed 
ce02c16fe28d: Pushed 
efafae78d70c: Mounted from library/ubuntu 
latest: digest: sha256:93c7bf1d9c82762eca41184e1609462c3b22283d8db013ef51c08bfa8c1e7464 size: 1155
```