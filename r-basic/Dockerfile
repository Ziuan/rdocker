FROM niclaslindstedt/r-min
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-07-17

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y \
    libssh-dev \
    libssh2-1-dev \
    libcurl4-openssl-dev \
    libxml2-dev
RUN R -e "install.packages('devtools', dependencies = TRUE, repos = 'http://cran.us.r-project.org')"

ENTRYPOINT ["/usr/bin/R"]
CMD ["--help"]

