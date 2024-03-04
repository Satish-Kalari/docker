DOCKER COMMANDS
----------------

	docker images --> shows existing images
	docker images -a -q ---> will show all images ids (-a =all, -q =id)
	docker images --filter label=TRAINER=Sivakumar
		-> To fnd images based of labels (for details go to line 334)
	docker images --no-trunc 
		-> no truncation of the lines when displaying image details 

	docker pull nginx 
		---> pulls the latest nginx image from docker hub
	docker pull nginx:stable-bulleseye 
		--> pulls stable-bulleseye nginx image from docker hub

	docker create <image ID> or <image name>:version 
		--> creates container for that image and version 
		docker create nginx:latest
		---> create nginx latest image into container container  
		---> this will not start the container, we need to start it manually
	
	docker rmi <image ID> or <image name>---> will remove that image
	docker rmi `docker images -a -q` ---> will remove all images  (` this is tilt symbol, on ~ bottom)
		-> this will remove all images
		-> this will not remove running containers
		-> this will not remove images that are used by running containers
		-> this will remove images that are not used by any container
	
	docker inspect <image name> or <image id>
		-> to inspect image
		
	docker ps --> shows running containers
	docker ps -a --> shows containers in all status 
	
	docker start <container ID> ---> will start that container
	docker stop <container ID> ---> will stop that container
	docker rm <container ID> ---> will remove that container (cant remove running containers, first need to stop it)
	docker rm -f <container ID> ---> will remove that container with out stopping
	docker rm -f `docker ps -a -q`---> will remove all container in all status 

# Docker build commands
	-> docker build -t <image name>:<image version> <path to docker file>
		-> -t = tag
		-> <image name> = name of the image
		-> <image version> = version of the image
		-> <path to docker file> = path to the docker file
		-> example: docker build -t nginx:latest /home/ubuntu/nginx/Dockerfile
		-> example: docker build -t nginx:latest / 
		-> example: docker build -t nginx:latest .

***pull+create+start = docker run***
	
	docker run nginx  
		-> this will pull latest nginx, creates container and start container 
		-> runs in foreground, 
		-> attached to screen 
		-> if interrupted it will exit any stage
	docker run -d nginx 
		-> this will pull latest nginx, creates container and start container 
		-> runs in background, 
		-> detached from screen 
		-> (-d = detach)
	docker run -d -p 8080:80 nginx
		-> (-d = detach)
		-> (-p = port)
		-> 8080 = host port (we can give any port that is not in use between 0-65,535)
		-> 80 = container port (here container is nginx, so we need to give port assigned to nginx, i.e 80)
			--> we can create multiple host port to connect multiple nginx container with static website from single docker ec2 instance
				-> <ec2 ip>:8080:80
				-> <ec2 ip>:8081:80
				-> <ec2 ip>:8082:80
	
	docker run -d -p 8080:80 --name nginx_projoy nginx
		-> --name will name container with your chosen name (example here is: nginx_projoy)
		-> if we do not give name system automatically provide some random names
		
	docker exec -it <container name> or <container id> bash
		-> this command allow login into a container
		->(here `i` is for input `t` is for terminal)
		
	docker inspect <container name> or <container id>
		-> to inspect container
	
	docker run -d -it <image name>:<image version>
		-> command starts a container in detached mode with an interactive terminal, which means the container runs in the background but still attaches to the terminal, 
			allowing the user to interact with the container's shell.
			-->  In other words, the -it option allows the user to enter commands into the container's shell. This is useful for debugging or troubleshooting purposes

Docker command to push images to docker hub
	-> docker push <image name>:<image version>

Docker command to push images to other hubs 
	-> docker tag <image name>:<image version> <hub name>/<image name>:<image version>
		-> example: docker tag nginx:latest projoy/nginx:latest
	-> docker push <hub name>/<image name>:<image version>
		-> example: docker push projoy/nginx:latest