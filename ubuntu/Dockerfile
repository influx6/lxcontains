FROM ubuntu

MAINTAINER EWETUMO ALEXANDER 	<trinoxf@gmail.com>


RUN apt-get update -y
RUN apt-get install -y software-properties-common golang axel git
RUN apt-add-repository -y "ppa:ubuntu-lxc/stable"
RUN apt-get update -y
RUN apt-get install -y lxc libpcap-dev lxc-templates lxc-dev

RUN bash -c "cd /; axel https://storage.googleapis.com/golang/go1.8.src.tar.gz"
RUN bash -c "cd /; mkdir /go1.8; tar -xvzf go1.8.src.tar.gz -C /go1.8; mkdir -p /go/src/github.com"
RUN bash -c "rm /go1.8.src.tar.gz"
WORKDIR /go1.8/go/src
ENV GOROOT_BOOTSTRAP /usr/lib/go-1.6
RUN bash -c "OLDPATH='$PATH'; . ./make.bash '$@' --no-banner; PATH='$OLDPATH'"
ENV PATH "/go1.8/go/bin:/go/bin:$PATH"
ENV GOROOT /go1.8/go
ENV GOPATH /go/
