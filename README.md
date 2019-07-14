# Docker-lession
A simple start with my study dairy
## Start with knowledge
 - Open source image contain engine.
 - Based on `Go` language.
 - Can run at any `Linux` OS with copy some lights images.
 - Use `Sandbox` two dockers can not connect with each other.
 - Less and less it will take memory.
 ## About the Docker
 There is a github blog with  
 [Open source](https://github.com/docker/docker)  
 [Offical](http://www.docker.com)  
 ## Install at Ubuntu
 - Use offical website to install `wget -qO- https://get.docker.com/ | sh`
 - Use Ubuntu api install `sudo apt install docker.io`
 - Start docker `sudo systemctl start docker`
 - Grant the docker with rights `sudo systemctl enable docker`
 - Check the docker if it is well installed `docker -v`  
If you are well installed it will show up with *Docker version aa.bb.c, build dddddd*
 - If you do not want run docker with `sudo`, you can run with instruction `sudo usermod -aG docker [USERNAME]`
Relogin the user and do next.
 - Start the docker services `sudo service docker start`
 - Try to run with docker `docker run hello-world`
If you see the text like  
```
Hello from Docker!  
This message shows that your installation appears to be working correctly.  
```
**Congratulations you are prefect finished install docker**
## To use
View docker `man docker` or `docker COMMAND --help`
## Fix error during installed
if you failed to run the insturction `docker run hello-world`
```
Unable to find image 'hello-world:latest' locally  
```
Run with `sudo gedit /etc/docker daemonm.json` add  
```
{
    "registry-mirrors": ["[your docker mirror image url]"]
}
```
Then restart the docker services `systemctl restart docker` && `systemctl status docker`  
Redo the `docker run hello-world` you will see  
```
Unable to find image 'hello-world:latest' locally  
latest: Pulling from library/hello-world  
1b930d010525: Pull complete  
Digest: sha256:6540fc08ee6e6b7b63468dc3317e3303aae178cb8a45ed3123180328bcc1d20f  
Status: Downloaded newer image for hello-world:latest  
  
Hello from Docker!  
This message shows that your installation appears to be working correctly.  
  
To generate this message, Docker took the following steps:  
 1. The Docker client contacted the Docker daemon.  
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.  
    (amd64)  
 3. The Docker daemon created a new container from that image which runs the  
    executable that produces the output you are currently reading.  
 4. The Docker daemon streamed that output to the Docker client, which sent it  
    to your terminal.  
  
To try something more ambitious, you can run an Ubuntu container with:  
 $ docker run -it ubuntu bash  
  
Share images, automate workflows, and more with a free Docker ID:  
 https://hub.docker.com/  
  
For more examples and ideas, visit:  
 https://docs.docker.com/get-started/  
```
**Okey this is the end to record "How To Install Docker"**  
*Have a good day :)*  
*Powered by moonhead*
