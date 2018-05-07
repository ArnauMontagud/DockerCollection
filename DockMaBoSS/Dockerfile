FROM centos:7 
# Version informations 
MAINTAINER Arnau Montagud <arnau.montagud@gmail.com> 
LABEL version="1.0"
## install dependencies RUN yum update -y && yum install -y git
RUN yum update -y \
	&& yum groupinstall -y "Development tools" \
	&& yum install -y \
		wget \
		which \
		tar \
		flex \
		bison

# add python2, python3, matplotlib, matplotlib.gridspec, matplotlib.patches, matplotlib.pylab, numpy, pandas, seaborn, xlsxwriter
# RUN yum -y install epel-release && yum clean all
# RUN yum -y install python-pip && yum clean all
RUN yum install -y epel-release \
&& yum -y update \
&& yum -y groupinstall "Development Tools" \
&& yum -y install python-devel \
&& yum -y install blas --enablerepo=epel \
&& yum -y install lapack --enablerepo=epel \
&& yum -y install Cython --enablerepo=epel \
&& yum -y install python-pip

RUN pip install boto3 \
&& pip install numpy \
&& pip install pandas \
&& pip install scipy

## download PhysiBoSS srcs from GitHub WORKDIR /home/
#RUN git clone https://github.com/gletort/PhysiBoSS.git

# compile MaBoSS in centos
# download from http://maboss.curie.fr/pub/MaBoSS-env-2.0.tgz
RUN wget  http://maboss.curie.fr/pub/MaBoSS-env-2.0.tgz \
	&& tar xvfz MaBoSS-env-2.0.tgz \
	&& cd MaBoSS-env-2.0/ \
	&& ./check-requirements.sh
#RUN cd engine/src \
#	&& make install \
#	&& make MAXNODES=150 install \
#	&& source ./MaBoSS.env

## compile PhysiBoSS RUN cd PhysiBoSS; make install;
# create directory where to mount local folders to run the simulation inside RUN mkdir running
CMD [""]

