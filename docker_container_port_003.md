docker container run -i -t --name web nginx bash 
1. -t means attach the terminal and show the terminal 
2. -d means run in deattach mode or in deamon mode or in background 
3. first image is searched locally and goes to registry to pull the images and if no tag is mentioned then pulls latest
4. docker container logs container_id to find all the logs of the application that container is running currently .
5. docker container pause container_id to pause the container 
6. docker container unpause container_id to upause the container 
7. docker container stop container_id to stop the container 
8. docker container create imange_name (seaches locally and if not found then goes to default registry)
   this will create the container and it's status will be created 
9. all server line container should be executed in deattach mode .
10. docker container remove container_name/container_id to remove the container 
11. docker container inspect container_name/container_id we need to find the ip address
11. to access container from outside we have to do port publishing
12. there are 2 ways of port publishing (random and fixed port publishing)
13. random port mapping is also called random port mapping 
   docker container run -d --name web -P nginx
   here we are using captial p 
   with exposed port mapping 
     "Ports": {
                "80/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "32768"
                    }
                ]
	without exposed port mapping 
	     "ExposedPorts": {
                "80/tcp": {}
            },
	this is the output of docker container inspect container_name/container_id 
	
	PORTS :-> 0.0.0.0:32768->80/tcp this will be the output od docker container ls 
14. to assign a fixed port ::==> docker container run -d --name container_namew -p local_system_port:docker_exposed_port image_name
                                 docker container run -d --name web -p 4444:80 nginx
								 here localhost 4444 port is synced with docker port 80.
							
15. -p  or -P is used to publish the port from docker to localhost and if localhost is reachable over internet then we can access it over internet.
