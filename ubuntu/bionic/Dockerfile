FROM ubuntu:bionic-20200112
RUN apt-get update && apt-get install -y software-properties-common curl
RUN curl -R -L -O http://drbl.nchc.org.tw/GPG-KEY-DRBL; apt-key add GPG-KEY-DRBL
RUN apt-add-repository 'deb http://free.nchc.org.tw/drbl-core drbl stable testing unstable dev'
RUN apt-get update && apt-get install -y partclone
CMD ["/bin/bash"]
