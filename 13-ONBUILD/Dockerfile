FROM almalinux:8
RUN yum install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
ONBUILD ADD index.html /usr/share/nginx/html/
CMD ["nginx","-g","daemon off;"]

# ONBUILD power author of image to force user of image to follow rules and regulation
#	--> this command wont run during build time 
#	--> only runs when another user using it