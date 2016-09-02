FROM debian:jessie

MAINTAINER mula.d.m@gmail.com

ENV RSYSLOG_SERVER rsyslog_server

RUN apt-get update && \
	apt-get dist-upgrade -yyqq && \
	apt-get install rsyslog -yyqq && \
    echo "*.* @@$RSYSLOG_SERVER:514" >>  /etc/rsyslog.conf

ENTRYPOINT [ "rsyslogd", "-n" ]
