FROM centos:7
LABEL maintainer="Arnau Montagud <arnau.montagud@gmail.com>"

RUN yum -y update && yum clean all
RUN yum -y install perl perl-core && yum clean all

RUN yum install -y wget && \
yum install -y java-1.7.0-openjdk-headless && \
yum clean all

RUN yum install -y ed less vim ca-certificates && \
yum clean all

#RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
#	&& locale-gen en_US.utf8 \
#	&& /usr/sbin/update-locale LANG=en_US.UTF-8
#ENV LC_ALL en_US.UTF-8
#ENV LANG en_US.UTF-8
#ENV R_BASE_VERSION 3.4.1

RUN yum install -y R-core R-devel R-littler rstudio && \
yum clean all

RUN useradd docker \
	&& mkdir /home/docker \
	&& chown docker:docker /home/docker \
	&& addgroup docker staff

	
CMD ["/bin/bash"]
