# How to build this:
# docker build -t gcr.io/${GOOGLE_CLOUD_PROJECT}/qperf --squash .

FROM centos/7

RUN yum update -y && yum install qperf -y && \
        yum clean all && \
        rm -rf /var/cache/yum

# Don't pass run argumets to act as a server.
# If you want to make this a client, run using the following:
# docker run --entrypoint qperf --qperf -ip 19766 -t 60 --use_bits_per_sec  <server hostname or ip address> tcp_bw
# Optionally:
# docker run --entrypoint qperf -vvs  <server hostname or ip address> tcp_lat
ENTRYPOINT [ "qperf"]