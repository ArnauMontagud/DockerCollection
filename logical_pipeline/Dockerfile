FROM centos:7
LABEL maintainer="Arnau Montagud <arnau.montagud@gmail.com>"

RUN yum -y update && yum clean all
RUN yum -y install perl perl-core && yum clean all
RUN yum install -y wget && \
yum install -y java-1.7.0-openjdk-headless && \
yum clean all

# Set environment variables.
ENV HOME /root
# Define working directory.
WORKDIR /root

FROM rocker/rstudio

CMD ["/bin/bash"]

