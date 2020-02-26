FROM alpine:3.7.3
RUN apk add git build-base autoconf automake libtool gettext \
util-linux-dev e2fsprogs-dev ncurses-dev ntfs-3g-dev linux-headers libressl-dev
WORKDIR /build
#RUN wget http://partclone.nchc.org.tw/download/unstable/partclone-0.3.13.tar.gz
#RUN tar xvf partclone-0.3.13.tar.gz
#WORKDIR /build/partclone-0.3.13
RUN git clone https://github.com/Thomas-Tsai/partclone.git
WORKDIR /build/partclone
RUN libtoolize --force --copy
RUN aclocal -I m4
RUN autoconf
RUN autoheader
RUN automake --add-missing --copy
RUN ./configure --enable-ncursesw --enable-extfs --enable-minix --enable-btrfs --enable-f2fs --enable-exfat --enable-ntfs
RUN make
