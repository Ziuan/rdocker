FROM niclaslindstedt/r-basic
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-07-17

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y \
  software-properties-common
RUN add-apt-repository -y \
  ppa:webupd8team/java && \
  apt-get update
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y \
  oracle-java8-installer r-cran-rjava
RUN echo /usr/lib/jvm/java-8-oracle/jre/lib/amd64 > /etc/ld.so.conf.d/java.conf && \
  echo /usr/lib/jvm/java-8-oracle/jre/lib/amd64/server >> /etc/ld.so.conf.d/java.conf && \
  ldconfig
RUN R CMD javareconf
RUN R -e "install.packages('rJava', dependencies = TRUE, repos = 'http://cran.us.r-project.org')"

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]

