# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL 	io.openshift.expose-services="8080:http" \
	io.k8s.description="Basic child image with ONBUILD" \
	io.k8s.display-name="HTTP" \
	io.openshift.expose-services="8080:http" \
	io.openshift.tag="apache, httpd"

RUN sed -i "s/Listen 88/Listen 8088/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
	chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001

