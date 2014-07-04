Simple "hello world" test with Docker and Mono
===

This example will run a simple C# console application in a Ubuntu Docker container. 

The application will print "Hello Mono!" to the console.

Step 1
---

####Set up a vagrant box to run the example on

######Open a command prompt and run:

    $ vagrant init phusion/ubuntu-14.04-amd64
    $ vagrant up
    
######SSH into the VM with:

    $ vagrant ssh

######Install Docker in the VM with:

     $ sudo apt-get update
     $ sudo apt-get install docker.io
     $ sudo ln -sf /usr/bin/docker.io /usr/local/bin/docker
     $ sudo sed -i '$acomplete -F _docker docker' /etc/bash_completion.d/docker.io


Step 2
---
######Copy the "MonoDockerTest" folder to the VM with SCP:

    $ scp -P 2222 -r MonoDockerTest vagrant@127.0.0.1:/home/vagrant/DockerTest/
    
username: vagrant

password: vagrant

Step 3
---
######In the VM:

1. Navigate to the folder with the Dockerfile
 
2. Build the Docker image with the following command:



       $ sudo docker build -t hello .
     
     
      
3. Run the Docker container with the following command:

       
       
       $ sudo docker run hello
      
It should output:

    Hello Mono!