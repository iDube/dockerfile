FROM alpine:3.2

RUN apk add --update ca-certificates openssl tar && \
    wget https://github.com/etcd-io/etcd/releases/download/v3.3.9/etcd-v3.3.9-linux-amd64.tar.gz && \
    tar -zxvf etcd-v3.3.9-linux-amd64.tar.gz && \
    mv etcd-v3.3.9-linux-amd64/etcd* /usr/local/bin/ && \
    apk del --purge tar openssl && \
    rm -rf etcd-v3.3.9-linux-amd64* /var/cache/apk/*

ENV ETCDCTL_API 3

EXPOSE 2379 2380

CMD ["etcd"]