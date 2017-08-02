FROM centos:7
LABEL maintainer="Arnau Montagud <arnau.montagud@gmail.com>"

#FROM sherwind/centos-buildpack-deps:centos7
#MAINTAINER Sherwin Daganato <sherwin@daganato.com>

RUN yum -y update && yum clean all
RUN yum -y install perl perl-core && yum clean all
RUN curl -L https://raw.githubusercontent.com/miyagawa/cpanminus/master/cpanm | perl - #App::cpanminus \
    && cpanm Carton \
    && rm -rf /root/.cpanm

#CMD [ "perl", "-de0" ]
CMD ["/bin/bash"]
