FROM almalinux:8
RUN yum install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
#To copy file from local to image 
COPY index.html /usr/share/nginx/html/
#Both COPY and ADD copy file from local to image 
#ADD have two extra capabilities
	#-->(1) ADD can directly download files from internet
	#-->(2) ADD can directly untar the .tar files 
ADD https://raw.githubusercontent.com/daws-76s/notes/master/session-01.txt /tmp/
ADD sample-1.tar /tmp/
CMD ["nginx","-g","daemon off;"]