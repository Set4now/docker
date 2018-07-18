FROM centos:7

LABEL maintainer="Suman Deb"

COPY nginx.repo /etc/yum.repos.d/

RUN yum clean all && yum update -y && yum install nginx -y

RUN mkdir -p /var/www/html && chmod 755 /var/www/html

COPY index.html /var/www/html

RUN mkdir -p /etc/nginx/sites-available && mkdir -p /etc/nginx/sites-enabled

COPY mysite.conf /etc/nginx/sites-available/mysite.conf

RUN ln -s /etc/nginx/sites-available/mysite.conf /etc/nginx/sites-enabled/mysite.conf

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]



