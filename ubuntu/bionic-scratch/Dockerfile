FROM ubuntu:bionic-20200219
RUN apt-get update && \
apt-get install --no-install-recommends -y curl gnupg2 gpg-agent git libssl-dev ca-certificates
RUN curl -R -L -O http://drbl.nchc.org.tw/GPG-KEY-DRBL; apt-key add GPG-KEY-DRBL
RUN echo 'deb http://free.nchc.org.tw/drbl-core drbl stable testing unstable dev' >> /etc/apt/sources.list.d/drbl-core
RUN echo 'deb-src http://free.nchc.org.tw/drbl-core drbl stable testing unstable dev' >> /etc/apt/sources.list.d/drbl-core
RUN sed -i -e 's/^# deb-src/deb-src/' /etc/apt/sources.list
RUN apt-get update && apt-get build-dep --no-install-recommends -y partclone
WORKDIR /build
RUN git clone https://github.com/Thomas-Tsai/partclone.git
WORKDIR /build/partclone
RUN ./autogen
RUN ./configure
RUN make
RUN make install
