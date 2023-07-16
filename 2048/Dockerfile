# base-image
FROM  ubuntu:latest
# command to upgrade all the packages in ubuntu machine
RUN apt-get update
#loading the utilities
RUN apt-get install -y nginx zip curl
#doing the configuration
RUN echo "daemon off;" >>/etc/nginx/nginx.conf
#curl to get the repo content
RUN curl -o /var/www/html/master.zip -L https://codeload.github.com/gabrielecirulli/2048/zip/master
#unzip and delete the folder
RUN cd /var/www/html/ && unzip master && mv 2048-master/* . && rm -rf 2048-master 2048-master.zip
#expose port
EXPOSE 80

CMD ["/usr/sbin/nginx/","-c", "/etc/nginx/nginx.conf"]

