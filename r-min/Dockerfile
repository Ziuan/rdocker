FROM ubuntu:16.04
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-07-17

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get -y install apt-utils
RUN apt-get -y install apt-transport-https
RUN echo 'deb https://cran.rstudio.com/bin/linux/ubuntu xenial/' >> /etc/apt/sources.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 51716619E084DAB9
RUN apt-get -y install r-base r-base-dev

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]
