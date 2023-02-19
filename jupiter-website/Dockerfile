FROM  amazonlinux:latest 

# install all needed dependencies
RUN yum update -y && \
    yum install -y httpd && \
    yum yum search wget && \
    yum install wget -y && \
    yum instal unzip -y


# change direcotry to httpd html dir 

RUN cd /var/www/html

# download website files
RUN wget https://github.com/azeezsalu/jupiter/archive/refs/heads/main.zip 

#unzip downloaded zip file
RUN upzip main.zip

#copy content of unzipped file to www dir
RUN cp -r techmax-main/* /var/www/html 

# remove unwanted folder

RUN rm -rf techmax-main/*

#specify port
EXPOSE 80

#specify entry point
ENTRYPOINT [ "/usr/sbin/httpd", "-D", "FOREGROUND" ]

