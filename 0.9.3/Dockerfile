FROM centos:7

MAINTAINER Ranjandas A P <thejranjan@gmail.com>

RUN yum install -y epel-release && yum install -y thrift-devel R && yum clean all

ENV RHBASE_VER 1.2.1

RUN ln -s /usr/include/thrift/* /usr/include/

RUN curl -o rhbase_$RHBASE_VER.tar.gz -LO https://github.com/RevolutionAnalytics/rhbase/blob/master/build/rhbase_$RHBASE_VER.tar.gz?raw=true && R CMD INSTALL rhbase_$RHBASE_VER.tar.gz

CMD ["R"]
