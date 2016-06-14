FROM centos:6

MAINTAINER Ranjandas A P <thejranjan@gmail.com>

RUN yum -y install automake \
					libtool \
					flex \
					bison \
					pkgconfig \
					gcc-c++ \
					boost-devel \
					libevent-devel \
					zlib-devel \
					python-devel \
					ruby-devel \
					openssl-devel \
					epel-release \
					&& yum -y install R \
					&& yum clean all

ENV THRIFT_VER 0.8.0
ENV RHBASE_VER 1.2.1

RUN curl -LO http://archive.apache.org/dist/thrift/$THRIFT_VER/thrift-$THRIFT_VER.tar.gz && \
	tar -xzvf thrift-$THRIFT_VER.tar.gz -C /usr/local/src && \
	cd /usr/local/src/thrift-$THRIFT_VER && \
	./configure --without-ruby --without-python && \
	make && make install && \
	ln -s /usr/local/lib/libthrift-$THRIFT_VER.so /usr/lib64/ && \
	make clean all && rm /thrift-$THRIFT_VER.tar.gz

ENV PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig

RUN curl -o rhbase_$RHBASE_VER.tar.gz -LO https://github.com/RevolutionAnalytics/rhbase/blob/master/build/rhbase_$RHBASE_VER.tar.gz?raw=true && R CMD INSTALL rhbase_$RHBASE_VER.tar.gz

CMD ["R"]
