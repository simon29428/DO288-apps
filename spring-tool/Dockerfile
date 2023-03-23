# spring-tool
FROM eclipse-temurin:17.0.6_10-jdk

# TODO: Set labels used in OpenShift to describe the builder image
#LABEL io.k8s.description="Platform for building xyz" \
#      io.k8s.display-name="builder x.y.z" \
#      io.openshift.expose-services="8080:http" \
#      io.openshift.tags="builder,x.y.z,etc."


COPY ./s2i/bin/ /usr/libexec/s2i

RUN mkdir /app-root

RUN chown -R 1001:1001 /app-root

# This default user is created in the openshift/base-centos7 image
USER 1001

EXPOSE 8080

CMD ["/usr/libexec/s2i/usage"]
