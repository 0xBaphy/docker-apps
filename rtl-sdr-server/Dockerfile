FROM alpine:latest

RUN apk add --no-cache musl-dev gcc make cmake pkgconf git libusb-dev

RUN git clone git://git.osmocom.org/rtl-sdr.git

WORKDIR rtl-sdr/build

RUN cmake ../ -DDETACH_KERNEL_DRIVER=ON -DINSTALL_UDEV_RULES=ON

RUN make && make install

RUN echo -e "blacklist dvb_usb_rtl28xxu\nblacklist rtl2832\nblacklist rtl2830" > tee -a /etc/modprobe.d/blacklist-rtl.conf

CMD ["rtl_tcp", "-a", "0.0.0.0"]
