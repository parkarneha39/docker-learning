## Why are Docker containers lightweight?
  * contains the base image (application + libraries + system dependecies)
  * share the resources from the host on which they are installed

   <img width="918" height="399" alt="image" src="https://github.com/user-attachments/assets/40e63063-1cb0-45e5-81e2-5d1db8823031" />


## Logical Isolation between containers

## 1. Files and Folders in containers base images
```
    /bin: contains binary executable files, such as the ls, cp, and ps commands.

    /sbin: contains system binary executable files, such as the init and shutdown commands.

    /etc: contains configuration files for various system services.

    /lib: contains library files that are used by the binary executables.

    /usr: contains user-related files and utilities, such as applications, libraries, and documentation.

    /var: contains variable data, such as log files, spool files, and temporary files.

    /root: is the home directory of the root user.
```

## 2. Files and Folders that containers use from host operating system
```
    The host's file system: Docker containers can access the host file system using bind mounts, which allow the container to read and write files in the host file system.

    Networking stack: The host's networking stack is used to provide network connectivity to the container. Docker containers can be connected to the host's network directly or through a virtual network.

    System calls: The host's kernel handles system calls from the container, which is how the container accesses the host's resources, such as CPU, memory, and I/O.

    Namespaces: Docker containers use Linux namespaces to create isolated environments for the container's processes. Namespaces provide isolation for resources such as the file system, process ID, and network.

    Control groups (cgroups): Docker containers use cgroups to limit and control the amount of resources, such as CPU, memory, and I/O, that a container can access.
```

## Docker Architecture

<img width="931" height="572" alt="image" src="https://github.com/user-attachments/assets/5f65f4bd-7615-427b-ac67-6d02f94ee906" />

> docker daemon is the heart of Docker
> If Docker daemon goes down, Docker stops
> Daemon takes the commands from client and executes them


## Docker Lifecycle

1. docker build - creates docker images from Dockerfile
2. docker run - creates container from the image
3. docker push - push the container to docker hub

## Docker terminology

1. Docker Daemon - heart
2. Docker client - CLI
3. Docker Desktop
4. Docker registries - save your docker images
5. Dockerfile - write set of instructions
6. Images - 


