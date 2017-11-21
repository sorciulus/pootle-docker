FROM webdevops/bootstrap:ubuntu-16.04

ENV POOTLE_VERSION="2.9.0"

RUN chmod -R 2777 /tmp
# Install apt packages
RUN /usr/local/bin/apt-install build-essential \
  swig \
  git \
  xmlstarlet \
  xsltproc \
  zip \
  cron \  
  unzip \
  mysql-client \
  openssh-client \
  python-dev \
  libxml2-dev \
  libssl-dev \
  libxslt1-dev \
  zlib1g-dev \
  libmysqlclient-dev \
  python-pip \
  python-xapian \
  xapian-tools \
  python-setuptools \
  nano
# Install python packages
RUN pip install -q virtualenv \
    MySQL-python \
    flup \
    python-memcached \
    python-Levenshtein \
    m2crypto \
    wheel

#Upgrade pip
RUN pip install --upgrade pip
# Install
RUN pip install -I --process-dependency-links --pre Pootle
# Configure pootle
COPY pootle.conf /root/.pootle/pootle.conf 
RUN mkdir -p /srv/pootle/po/.tmp   

WORKDIR /home/pootle

EXPOSE 8000
VOLUME ["/usr/local/lib/python2.7/dist-packages/pootle"]
COPY pootle.sh /pootle.sh
RUN chmod a+x /pootle.sh
CMD ["/pootle.sh"]