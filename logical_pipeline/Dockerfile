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

#RUN yum install -y R-core && \
#yum install -y R-devel && \
#yum install -y R-littler && \
#yum install -y rstudio && \
#yum clean all

RUN yum install -y epel-release
RUN yum install R -y
RUN yum install -y rstudio
RUN yum clean all

#RUN wget https://download2.rstudio.org/rstudio-server-rhel-1.0.44-x86_64.rpm
#RUN yum install --nogpgcheck rstudio-server-rhel-1.0.44-x86_64.rpm -y
RUN firewall-cmd --permanent --zone=public --add-port=8787/tcp

RUN useradd docker \
	&& mkdir /home/docker \
	&& chown docker:docker /home/docker \
	&& addgroup docker staff

	
CMD ["/bin/bash"]  
