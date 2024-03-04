FROM almalinux:8
# docker run entry:v1 ping yahoo.com works here
#CMD ["ping", "google.com"]
# docker run entry:v1 ping yahoo.com wont work here
#ENTRYPOINT ["ping", "google.com"]
CMD ["google.com"]
ENTRYPOINT ["ping"]
# ***CDM command can be overdridden by another command at run time***
# ***ENTRYPOINT command can't be overdridden***
#		->if you try to do so, the command we entered in cli at run time will go and append to ENTRYPOINT
#		-> For best results use CMD and ENTRYPOINT in combination
#			--> We can use CMD instruction to supply arrguments to ENTRYPOINT
#			--> we can always override CDM arguments from run time 