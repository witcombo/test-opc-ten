FROM harbor.vipkid-qa.com.cn/public/sgplm-ep:v1.1
LABEL vendor=VipKid\ OnlineClass \
      sgplm-dispatcher.is-production="" \
      sgplm-dispatcher.version="1.1" \
      sgplm-dispatcher.release-date="2019-06-06"


RUN mkdir -p /usr/local/dispatcher/ /data/logs/dispatcher
COPY dispatcher /usr/local/dispatcher/dispatcher-etcd.jar
COPY keyStore.p12 /usr/local/dispatcher
COPY application.properties /usr/local/dispatcher
