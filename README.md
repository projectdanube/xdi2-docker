<a href="http://projectdanube.org/" target="_blank"><img src="http://projectdanube.github.com/xdi2/images/projectdanube_logo.png" align="right"></a>
<img src="http://projectdanube.github.com/xdi2/images/logo64.png"><br>

Dockerfiles for the [XDI2](http://github.com/projectdanube/xdi2) server.

### How to build

First, you need to build the main [XDI2](http://github.com/projectdanube/xdi2) project.

To build a base Docker for the latest XDI2 code

	cd xdi2
    docker build -t projectdanube/xdi2:latest .
    cd ..

To build a Docker image for xdi2-transport-http-war

	cd xdi2-transport-http-war
    docker build -t projectdanube/xdi2-transport-http-war:latest .
    cd ..

To build a Docker image for xdi2-webtools

	cd xdi2-webtools
    docker build -t projectdanube/xdi2-webtools:latest .
    cd ..

To build a Docker image for xdi2-selfhosted

	cd xdi2-selfhosted
    docker build -t projectdanube/xdi2-selfhosted:latest .
    cd ..

### How to run

To run the Docker image for the xdi2-transport-http-war in a new container

	docker run -d -p 8080:8080 projectdanube/xdi2-transport-http-war:latest

To run the Docker image for the xdi2-webtools in a new container

	docker run -d -p 8080:8080 projectdanube/xdi2-webtools:latest

To run the Docker image for the xdi2-selfhosted in a new container

	docker run -d -p 8080:8080 projectdanube/xdi2-selfhosted:latest

### Community

Google Group: http://groups.google.com/group/xdi2

IRC: irc://irc.freenode.net:6667/xdi
