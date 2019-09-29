FROM rhel7-init
RUN yum -y install httpd; yum clean all; systemctl enable httpd;
RUN mkdir -p /var/www/html/pub/files
RUN chown root:apache /var/www/html/pub
RUN chmod -R 755 /var/www/html/pub
RUN echo "Provides CoresOS Installation Files" > /var/www/html/index.html
copy welcome.conf /etc/httpd/conf.d/welcome.conf
RUN chown root /etc/httpd/conf.d/welcome.conf
RUN mkdir /etc/systemd/system/httpd.service.d/; echo -e '[Service]\nRestart=always' > /etc/systemd/system/httpd.service.d/httpd.conf
EXPOSE 80
CMD [ "/sbin/init" ]
