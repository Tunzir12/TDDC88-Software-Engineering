## Lab 1 - Docker

### 2.1
            //lists all the files and directories under a specified directory.
            $ ls
            //returns the the name of the operating system
            $ uname -a 
            -> Linux debian 6.1.0-21-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.90-1 (2024-05-03) x86_64 GNU/Linux


### 2.2 

#####  docker run alpine
        Unable to find image 'alpine:latest' locally
        latest: Pulling from library/alpine
        43c4264eed91: Pull complete 
        Digest: sha256:beefdbd8a1da6d2915566fde36db9db0b524eb737fc57cd1367effd16dc0d06d
        Status: Downloaded newer image for alpine:latest
 Repeating 2.1 commands but the output is same as before.

 ##### docker run -it alpine ls
        bin    etc    lib    mnt    proc   run    srv    tmp    var
        dev    home   media  opt    root   sbin   sys    usr

##### docker run -it alpine uname -a
        Linux ec87f2a2c100 6.1.0-21-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.90-1 (2024-05-03) x86_64 Linux

##### docker images

        REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
        alpine        latest    91ef0af61f39   2 days ago      7.8MB
        hello-world   latest    d2c94e258dcb   16 months ago   13.3kB

### 2.4 

##### student@debian:~$ docker ps
        CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
### 2.5

##### student@debian:~$ docker ps -a
        CONTAINER ID   IMAGE         COMMAND      CREATED          STATUS                      PORTS     NAMES
        ec87f2a2c100   alpine        "uname -a"   9 minutes ago    Exited (0) 9 minutes ago              modest_mestorf
        e06e2dac74b1   alpine        "ls"         10 minutes ago   Exited (0) 10 minutes ago             laughing_mahavira
        25ae66f782bd   alpine        "/bin/sh"    17 minutes ago   Exited (0) 17 minutes ago             flamboyant_herschel
        85e9eb7c460d   hello-world   "/hello"     5 days ago       Exited (0) 5 days ago                 gallant_bhabha

-a access the hidden files along with all other files in linux

### 2.6 
##### student@debian:~$ docker rm e06e2dac74b1
        e06e2dac74b1
##### student@debian:~$ docker rm 25ae66f782bd
        25ae66f782bd
##### student@debian:~$ docker ps -a
        CONTAINER ID   IMAGE         COMMAND    CREATED      STATUS                  PORTS     NAMES
        85e9eb7c460d   hello-world   "/hello"   5 days ago   Exited (0) 5 days ago             gallant_bhabha

  

### part 3 step 4

    Dockerfile provides instructions to the image builder on the commands to run, files to copy, startup command, and more.
    
    FROM <image> - this specifies the base image that the build will extend. here the base is python.

    WORKDIR <path> - this instruction specifies the "working directory" or the path in the image where files will be copied and commands will be executed.

    COPY <host-path> <image-path> - this instruction tells the builder to copy files from the host and put them into the container image.
    
    EXPOSE <port-number> - this instruction sets configuration on the image that indicates a port the image would like to expose.
    
    CMD ["<command>", "<arg1>"] - this instruction sets the default command a container using this image will run.

### part 3 step 5

    We are working on a child image as it refers base as python. 

##### 1. What is Docker, and how does it differ from traditional virtualization?

Docker is an open-source containerization platform where developers can develop, test, ship and run their programs without worrying about developer's infrastructure. The use of containers makes it easier to run on any IT infrastructure.

###### Docker v/s Traditional virtualization

Virtual machines have the 'Host OS' and 'Guest OS' in their architecture where the virtual machines acts like a physical computer on a host computer. For each Virtual machines, guest OS is needed to be booted up. Therefore, it virtulizes the system kernal and application layer. On the other hand, Docker only virtualizes the application layer by sharing the Host OS between the containers. It makes it light and faster to boot than virtual machines as it does not need the boot Guest OS to run the application.

##### 2. What is the purpose of a Dockerfile in the image-building process?



##### 3. What does the FROM instruction in the Dockerfile do, and why is it important?
##### 4. Explain the purpose of the COPY instruction in the Dockerfile.
##### 5. What does the CMD instruction in the Dockerfile define, and why is it important?

