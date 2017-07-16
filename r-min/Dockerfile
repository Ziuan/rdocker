FROM ubuntu:16.04
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-07-16

RUN echo "deb http://archive.ubuntu.com/ubuntu xenial main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get -yqq install apt-transport-https
RUN echo 'deb https://cran.rstudio.com/bin/linux/ubuntu xenial' >> /etc/apt/sources.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 51716619E084DAB9
RUN apt-get -yqq install r-base r-base-dev

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]
