FROM  amazonlinux:latest 

# install all needed dependencies
RUN yum update -y && \
    yum install -y httpd && \
    yum install wget -y && \
    yum install unzip -y

# change direcotry to httpd html dir 
RUN cd /var/www/html

# download website files
RUN wget https://github.com/azeezsalu/techmax/archive/refs/heads/main.zip

# unzip folder
RUN unzip main.zip

# copy files into html directory
RUN cp -r techmax-main/*  /var/www/html/

# remove unwanted folder
RUN rm -rf techmax-main main.zip

#specify port
EXPOSE 80

#specify entry point
ENTRYPOINT [ "/usr/sbin/httpd", "-D", "FOREGROUND" ]

