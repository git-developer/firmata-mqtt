FROM alpine
RUN apk add mosquitto-clients perl-device-serialport perl-try-tiny
RUN apk add perl-app-cpanminus wget make && \
    cpanm Device::Firmata && \
    apk del perl-app-cpanminus wget make && \
    rm -r /root/.cpanm
COPY observe-firmata-input mqtt-publish /opt/firmata-mqtt/
CMD exec /opt/firmata-mqtt/observe-firmata-input
