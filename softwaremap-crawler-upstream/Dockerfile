FROM centos:centos7

MAINTAINER Maxime Choffat <maxime.choffat@gmail.com>
MAINTAINER Antoine Moser <antoine.moser@gmail.com>

RUN curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -

RUN yum update -y
RUN yum install -y nodejs

ENV NGINX_ROOT_FOLDER /project/
VOLUME [ "$NGINX_ROOT_FOLDER" ]

EXPOSE 5000

CMD ["node", "/project/softwaremap-crawlers/nginx-upstream-html/start-server.js", ">", "/dev/stdout"]