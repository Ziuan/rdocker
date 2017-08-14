FROM ubuntu:16.04
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-08-14

# r-min
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections \
  && apt-get update \
  && apt-get upgrade -y \
  && apt-get -y install apt-transport-https \
  && echo 'deb https://cran.rstudio.com/bin/linux/ubuntu xenial/' >> /etc/apt/sources.list \
  && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 51716619E084DAB9 \
  && apt-get -y install \
       r-base \
       r-base-dev \

# r-basic
  && apt-get install -y \
       libssh-dev \
       libssh2-1-dev \
       libcurl4-openssl-dev \
       libxml2-dev \
  && R -e "install.packages('devtools', dependencies = TRUE, repos = 'http://cran.us.r-project.org')" \

# r-java
  && apt-get install -y \
       software-properties-common \
  && add-apt-repository -y \
       ppa:webupd8team/java \
  && apt-get update \
  && echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections \
  && apt-get install -y \
       oracle-java8-installer r-cran-rjava \
  && echo /usr/lib/jvm/java-8-oracle/jre/lib/amd64 > /etc/ld.so.conf.d/java.conf \
  && echo /usr/lib/jvm/java-8-oracle/jre/lib/amd64/server >> /etc/ld.so.conf.d/java.conf \
  && ldconfig \
  && R CMD javareconf \
  && R -e "install.packages('rJava', dependencies = TRUE, repos = 'http://cran.us.r-project.org')" \

# cleanup
  && apt-get remove --purge -y apt-transport-https \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /var/cache

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]

