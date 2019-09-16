##▶ docker build -t ex03 .
## docker run -it --rm -d -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03
FROM debian

LABEL maintainer="saolivei@student.42.us.org"

RUN apt-get update -y; apt-get install -y curl openssh-server ca-certificates postfix
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | /bin/bash
RUN apt-get install -y gitlab-ce


EXPOSE 443 80 22
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && /bin/bash
