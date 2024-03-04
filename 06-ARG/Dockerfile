# (1) ARG instruction can provide values to the Dockerfile only at buildtime
# (2) ENV instruction can provide values to the Dockerfile both at buildtime and runtime
# (3) ARG value defined before FROM will not be acessed after FROM instruction 
ARG version
# docker build -t arg:v1 --build-arg version=9 .
# Here :-8 means if user forgot to give version, then installs version 8
FROM almalinux:${version:-8}
ARG username
RUN adduser $username
USER $username
ARG COURSE
ARG TRAINER
RUN echo "Course: ${COURSE}, Trainer: ${TRAINER}, Version: ${version}"
ENV COURSE=${COURSE}
ENV TRAINER=${TRAINER}
CMD ["sleep","100"]
# docker build -t arg:v1 --build-arg username=satish .
# docker build -t arg:v1 --build-arg username=satish --build-arg COURSE=DevOps --build-arg TRAINER=sivakumar .
# docker build -t arg:v1 --build-arg username=satish --build-arg COURSE=DevOps --build-arg TRAINER=sivakumar --build-arg version=9 .

#How to use ARG inside containers
#	-> combine ARG and ENV
#	-> assign ARG values to ENV variables, so that we can access them at runtime