FROM harbor.vipkid-qa.com.cn/public/sgplm-ep:v1.1
LABEL vendor=VipKid\ OnlineClass \
      sgplm-signalproxy.is-production="" \
      sgplm-signalproxy.version="1.1" \
      sgplm-signalproxy.release-date="2019-06-06"

RUN mkdir -p /usr/local/signalproxy/cert /data/logs/signalproxy
COPY signalproxy conf.json /usr/local/signalproxy/
COPY cert /usr/local/signalproxy/cert
