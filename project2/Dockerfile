FROM ubuntu:18.04
ARG GIT_COMMIT_ID=unspecified
ARG JENKINS_BUILD_NUMBER=unspecified
LABEL git_commit=$GIT_COMMIT_ID
LABEL jenkins_build_number=$JENKINS_BUILD_NUMBER
RUN apt-get update && apt-get install -y apache2
EXPOSE 80
WORKDIR /var/www/html
COPY ./images ./images
COPY ./index.html .
RUN chmod -R o+r *
CMD ["apachectl", "-D", "FOREGROUND"]
