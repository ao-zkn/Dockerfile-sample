FROM centos:7

LABEL maintainer="masato arihara"

ENV JDK_VERSION 8u162
ENV JDK_BUILD_NO b12
ENV JDK_TAR_GZ jdk-${JDK_VERSION}-linux-x64.tar.gz
ENV JDK_DOWNLOAD_HASH 0da788060d494f5095bf8624735fa2f1
ENV JDK_DOWNLOAD_URL http://download.oracle.com/otn-pub/java/jdk/${JDK_VERSION}-${JDK_BUILD_NO}/${JDK_DOWNLOAD_HASH}/${JDK_TAR_GZ}

ENV JAVA_HOME /usr/local/java

RUN yum -y update \
    && yum -y install wget \
    && mkdir -p ${JAVA_HOME} \
    && wget --no-cookies --no-check-certificate --header "Cookie: oraclelicense=accept-securebackup-cookie" ${JDK_DOWNLOAD_URL} \
    && tar -xzf ${JDK_TAR_GZ} -C ${JAVA_HOME} \
    && ln -s ${JAVA_HOME}/* ${JAVA_HOME}/default \
    && rm -rf ${JDK_TAR_GZ}
