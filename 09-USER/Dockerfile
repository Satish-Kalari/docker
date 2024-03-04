FROM almalinux:8
#Here RUN has root access to add user
RUN adduser satish
#For securtiy reason we dont want user have root access
# To remove user access we use USER here. Form this point onwards no more root access 
USER satish
CMD ["sleep", "100"]