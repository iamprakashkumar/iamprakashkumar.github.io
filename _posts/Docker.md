 
2: Create a custom Docker Image built from a Dockerfile and push it to a central registry where it can be pulled to be deployed on other environments. Learn about the union file system and copy-on-write, and how they help you deliver applications faster  
3: Deploy containers using Docker swarm and learn how Docker Swarm helps solve problems such as reconciliation, scaling, high availability and service discovery. In this lab, we'll use Play-with-Docker for a multi-node cluster rather than use your locally installed Docker.  
 
**Use Play-With-Docker**
Play-With-Docker, which is a website where we can run terminals directly from browser that have Docker installed.  

**Containers**  
Containers are just a process (or a group of processes) running in isolation, which is achieved with Linux namespaces and control groups.  
Linux namespaces and control groups are features that are built into the Linux kernel. Other than the Linux kernel itself, there is nothing special about containers.  

![VM vs Docker](https://raw.githubusercontent.com/prakashnoob/prakashnoob.github.io/master/_site/Images/docker.PNG)  

Each container has its own set of "namespaces" (isolated view)
 PID - Process ID
 USER - User and Group ID
 UTS - hostname and domainname
 NS - Mount point
 NET - Network devices, stacks, port
 IPC - Interprocess communication, message queue
 cgroup - controls limit and monitoring of resources.

We use Docker, which has been the understood standard tool for using containers to build applications.  
Docker provides developers and operators with a friendly interface to build, ship, and run containers on any environment.

1: Run our first container and learn how to inspect it. Explore the Docker Hub and discover common images ready to be run.   

