FROM amazonlinux:2022

ENV GOPATH=/go
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV GOBIN=$GOPATH/bin
ENV GOLANG_VERSION=1.18.2
ENV GO111MODULE on

RUN echo 'export PS1="${debian_chroot:+($debian_chroot)}\u@\h:\w\$"' >> /root/.bash_profile
RUN mkdir -p /usr/src/api_client
WORKDIR /usr/src/api_client



RUN yum update -y && \
    yum install -y tar && \
    yum install -y gzip && \
    yum install -y git && \
    yum install -y gcc && \
    yum install -y python && \
    yum install  -y python-pip && \
    curl -OL https://go.dev/dl/go1.18.2.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf ./go1.18.2.linux-amd64.tar.gz


RUN go install github.com/uudashr/gopkgs/v2/cmd/gopkgs@latest && \
  go install github.com/ramya-rao-a/go-outline@latest && \
  go install github.com/nsf/gocode@latest && \
  go install github.com/acroca/go-symbols@latest && \
  go install github.com/fatih/gomodifytags@latest && \
  go install github.com/josharian/impl@latest && \
  go install github.com/haya14busa/goplay/cmd/goplay@latest && \
  go install github.com/go-delve/delve/cmd/dlv@latest && \
  go install golang.org/x/lint/golint@latest && \
  go install golang.org/x/tools/gopls@latest && \
  go install github.com/rubenv/sql-migrate/...@latest 