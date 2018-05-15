FROM rocker/rstudio
# Version informations 
MAINTAINER Arnau Montagud <arnau.montagud@gmail.com> 
LABEL version="1.0"
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
		flex \
		bison \
		python3-pip \
		build-essential \
		python3-dev \
		python3-setuptools \
		python3-wheel

# download MaBoSS from http://maboss.curie.fr/pub/MaBoSS-env-2.0.tgz
RUN wget http://maboss.curie.fr/pub/MaBoSS-env-2.0.tgz \
	&& tar xvfz MaBoSS-env-2.0.tgz \
	&& cd MaBoSS-env-2.0/ \
	&& ./check-requirements.sh
# compile MaBoSS
RUN cd MaBoSS-env-2.0/engine/src/ \
	&& make install \
	&& make MAXNODES=150 install
# install python3 packages
RUN pip3 install numpy pandas matplotlib seaborn xlsxwriter
CMD ["/bin/bash"]

