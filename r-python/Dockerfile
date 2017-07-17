FROM niclaslindstedt/r-basic
MAINTAINER Niclas Lindtedt <nicl@slindstedt.se>
ENV REFRESHED_AT 2017-07-17

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y \
  python3-dev \
  python3-pip
RUN pip3 install --upgrade pip

ENTRYPOINT ["/usr/bin/python3"]
CMD ["--help"]

