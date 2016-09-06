FROM nginx:alpine

MAINTAINER mula.d.m@gmail.com

ENV RSYSLOG_AGENT rsyslog_agent

COPY nginx.conf.template /etc/nginx/nginx.conf.template
COPY default.conf.template /etc/nginx/conf.d/default.conf.template

EXPOSE 80 443

CMD sh -c "envsubst '\$RSYSLOG_AGENT' < /etc/nginx/conf.d/default.conf.template > /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'"


