FROM ubuntu:18.04
ARG GIT_COMMIT_ID=unspecified
ARG JENKINS_BUILD_NUMBER=unspecified
LABEL git_commit=$GIT_COMMIT_ID
LABEL jenkins_build_number=$JENKINS_BUILD_NUMBER
RUN apt-get update && apt-get install -y apache2
RUN sed -i 's/Listen\ 80/Listen\ 82/' /etc/apache2/ports.conf && sed -i 's/<VirtualHost: \*:80>/<VirtualHost: \*:82>/' /etc/apache2/sites-enabled/000-default.conf
EXPOSE 82
WORKDIR /var/www/html
COPY ./images ./images
COPY ./index.html .
RUN chmod -R o+r *
CMD ["apachectl", "-D", "FOREGROUND"]
