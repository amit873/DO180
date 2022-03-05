FROM ubi7/ubi:7.7
MAINTAINER 'Amit Kumar Gupta'
ENV PORT 8080
RUN yum install -y httpd && yum clean all
RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf
RUN chown -R apache:apache /etc/httpd/logs/
RUN chown -R apache:apache /run/httpd/
USER apache
EXPOSE ${PORT}
COPY ./src/ /var/www/html/
CMD ["httpd", "-D", "FOREGROUND"]
