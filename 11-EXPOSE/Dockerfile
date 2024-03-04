#almalinux is same as centos
# dockerfile always start with FROM
# exception: ARG command can come bofore FROM to povide values to FROM instruction
FROM almalinux:8
# RUN command install software or configurations during bulding image 
#RUN runs at the time of image building
RUN yum install nginx -y
#EXPOSE functions as a type of documentation between the person who builds the image and the person who runs the container
EXPOSE 80/tcp
#CMD runs at the time of container creation
CMD [ "nginx", "-g", "daemon off;" ]
