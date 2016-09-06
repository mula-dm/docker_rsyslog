FROM debian:jessie

MAINTAINER mula.d.m@gmail.com

ENV RSYSLOG_SERVER rsyslog_server

RUN apt-get update && \
	apt-get dist-upgrade -yyqq && \
	apt-get install rsyslog -yyqq && \
	sed 's/#$ModLoad imudp/$ModLoad imudp/' -i /etc/rsyslog.conf && \
	sed 's/#$UDPServerRun 514/$UDPServerRun 514/' -i /etc/rsyslog.conf && \
	sed 's/#$ModLoad imtcp/$ModLoad imtcp/' -i /etc/rsyslog.conf && \
	sed 's/#$InputTCPServerRun 514/$InputTCPServerRun 514/' -i /etc/rsyslog.conf && \
	sed 's/$ModLoad imklog/#$ModLoad imklog/' -i /etc/rsyslog.conf && \
	sed 's/$FileOwner syslog/$FileOwner root/' -i /etc/rsyslog.conf && \
	sed 's/$PrivDropToUser syslog/#$PrivDropToUser syslog/' -i /etc/rsyslog.conf && \
	sed 's/$PrivDropToGroup syslog/#$PrivDropToGroup syslog/' -i /etc/rsyslog.conf && \
	echo "*.* @@$RSYSLOG_SERVER:514" >>  /etc/rsyslog.conf

EXPOSE 514/tcp 514/udp

ENTRYPOINT [ "rsyslogd", "-n" ]
