FROM ubuntu:18.04

LABEL maintainer="Di Mou <moudi717@gmail.com>" \
      image="moudixtc/shadowsocks:latest"

ARG dumb_init_version=1.2.1
ARG dumb_init_path=/usr/local/bin/dumb-init

RUN apt-get update && \
    apt-get install -y curl git python3 python3-distutils && \
    curl -sSL https://bootstrap.pypa.io/get-pip.py | python3 && \
    curl -sSL -o ${dumb_init_path} https://github.com/Yelp/dumb-init/releases/download/v${dumb_init_version}/dumb-init_${dumb_init_version}_amd64 && \
    chmod +x ${dumb_init_path}

RUN pip3 install git+https://github.com/shadowsocks/shadowsocks.git@master && \
    mkdir -p /etc/shadowsocks

EXPOSE 8388

ENTRYPOINT ["dumb-init", "--"]
CMD ["/usr/local/bin/ssserver", "-c", "/etc/shadowsocks/shadowsocks.json"]
