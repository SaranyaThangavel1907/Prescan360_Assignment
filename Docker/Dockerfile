#Use CentOS as base
FROM centos:7.5.1804

RUN yum -y update
RUN yum -y install centos-release-scl

# Install custom tools
ENV VERSION 1.9.2
ENV FILE go$VERSION.linux-amd64.tar.gz
ENV URL https://golang.org/dl/go1.17.2.linux-amd64.tar.gz3

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN set -ex ; \
    yum -y update ; \
    yum -y install git rpm-build ; \
    yum -y clean all ; \
    curl -OL $URL ; \
	tar -C /usr/local -xzf $FILE ; \
	rm $FILE ; \
    mkdir -p "$GOPATH/src" "$GOPATH/bin"

RUN yum -y install devtoolset-7-gcc*
SHELL [ "/usr/bin/scl", "enable", "devtoolset-7"]
RUN gcc --version

WORKDIR $GOPATH
