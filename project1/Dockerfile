FROM hshar/webapp
ARG GIT_COMMIT_ID=unspecified
ARG JENKINS_BUILD_NUMBER=unspecified
LABEL git_commit_id=$GIT_COMMIT_ID
LABEL jenkins_build_number=$JENKINS_BUILD_NUMBER
WORKDIR /var/www/html
COPY ./images ./images
COPY ./index.html .
RUN chmod -R o+r *
CMD ["apachectl", "-D", "FOREGROUND"]
