FROM ubuntu:latest

LABEL maintainer="sensri"

RUN apt-get update -yq && \
    apt-get install -yq tini etcd-client fio sysstat ioping sed && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# The image contains multiple tools: etcdctl, fio, ioping, iostat, mpstat, sed.
# Use the tool name as the first argument when running the container.
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["/bin/bash"]
