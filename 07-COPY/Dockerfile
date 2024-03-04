#almalinux is same as centos
# dockerfile always start with FROM
# exception: ARG command can come bofore FROM to povide values to FROM instruction
FROM almalinux:8
# RUN command install software or configurations during bulding image 
#RUN runs at the time of image building
RUN yum install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
#To copy file from local to image
COPY index.html /usr/share/nginx/html/
#CMD runs at the time of container creation
CMD [ "nginx", "-g", "daemon off;" ]

