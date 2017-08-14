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

# cleanup
  && apt-get remove --purge -y apt-transport-https \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /var/cache

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]

