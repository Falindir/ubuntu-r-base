Bootstrap: docker
From: ubuntu:16.04
IncludeCmd: yes


%environment
  R_VERSION=3.2.5
  export R_VERSION
  R_CONFIG_DIR=/etc/R/
  export R_CONFIG_DIR

%labels
  Maintainer Remy Dernat
  Version v0.0.1
  R_Version 3.2.5
  BuildDate 2018 Jan 19

%apprun R
  exec R "$@"

%apprun Rscript
  exec Rscript "$@"

%runscript
  exec R "$@"

%post
  apt-get update
  apt-get install -y r-base r-base-dev libblas3 libblas-dev liblapack-dev liblapack3

  # installing some packages
  echo install.packages\(\"ade4\"\, repos\=\'https://cloud.r-project.org\'\) | R --slave
  echo install.packages\(\"ape\"\, repos\=\'https://cloud.r-project.org/\'\) | R --slave
  echo install.packages\(\"FD\"\, repos\=\'https://cloud.r-project.org/\'\) | R --slave
