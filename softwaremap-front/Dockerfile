FROM centos:centos7

MAINTAINER Maxime Choffat <maxime.choffat@gmail.com>
MAINTAINER Antoine Moser <antoine.moser@gmail.com>

RUN yum update -y
RUN yum install -y epel-release
RUN yum install -y nginx


ENV NGINX_ROOT_FOLDER /project/
VOLUME [ "$NGINX_ROOT_FOLDER" ]

ADD includes/ /etc/nginx/conf.d/

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
  && ln -sf /dev/stderr /var/log/nginx/error.log 

EXPOSE 8080
EXPOSE 9090

CMD ["nginx", "-g", "daemon off;"]