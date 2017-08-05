_Based on https://github.com/jaehyeon-kim/r-docker_

- **r-min:**
  - [x] Ubuntu 16.04
  - [x] apt packages: `r-base, r-base-dev`
  - **r-basic:**
    - [x] apt packages: `libssh-dev libssh2-1-dev libcurl4-openssl-dev libxml2-dev`
    - [x] R packages: devtools
    - **r-java:**
      - [x] apt packages: `software-properties-common oracle-java8-installer r-cran-rjava`
      - [x] R packages: rJava
      - **r-java-python:**
        - [x] apt packages: `python3-dev python3-pip`
    - **r-python:**
      - [x] apt packages: `python3-dev python3-pip`
