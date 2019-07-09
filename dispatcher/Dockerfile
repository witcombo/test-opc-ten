FROM harbor.vipkid-qa.com.cn/public/sgplm-ep:v1.1
LABEL vendor=VipKid\ OnlineClass \
      sgplm-dispatcher.is-production="" \
      sgplm-dispatcher.version="<build_tag>" \
      sgplm-dispatcher.release-date="2019-06-06"
MAINTAINER SignalingTeam "lichunpeng@vipkid.com.cn"

RUN mkdir -p /usr/local/dispatcher/ /data/logs/dispatcher
COPY dispatcher /usr/local/dispatcher/dispatcher-etcd.jar
COPY keyStore.p12 logback-spring.xml application.properties /usr/local/dispatcher
