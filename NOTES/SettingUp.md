DOCKER
---------------

Installing Docker on centos server (https://docs.docker.com/engine/install/centos/)
	t2.micro (30 gb)
	go to supperputty
	sudo su -
	yum install -y yum-utils
	yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
	yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
	systemctl start docker
	systemctl enable docker
	systemctl status docker
	
Docker user can only use docker command, when install docker a group called "docker" is created. need to add user to this group
command to add user to "Docker" group:
	-->usermod -aG docker centos
			here docker is the group
			& centos is the user
	-->after assign user logout and re login in putty

Container is the running version of image
image vs container
AMI vs EC2

installing docker compose
	-->curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
	-->chmod +x /usr/local/bin/docker-compose
	-->ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
	-->docker-compose --version

