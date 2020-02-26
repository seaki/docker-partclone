FROM ubuntu:bionic-20200112
RUN apt-get update && \
apt-get install --no-install-recommends -y curl gnupg2 gpg-agent ca-certificates
RUN curl -R -L -O http://drbl.nchc.org.tw/GPG-KEY-DRBL; apt-key add GPG-KEY-DRBL
RUN curl -R -L -O http://drbl.nchc.org.tw/GPG-KEY-DRBL; apt-key add GPG-KEY-DRBL
RUN echo 'deb http://free.nchc.org.tw/drbl-core drbl stable testing unstable dev' >> /etc/apt/sources.list.d/drbl-core
RUN apt-get update && apt-get install -y partclone
CMD ["/bin/bash"]
