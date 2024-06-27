FROM alpine:latest
LABEL MAINTAINER Dr.Rao
RUN apk add --update supervisor nginx && rm -rf /var/cache/apk.*
COPY strat.sh /script/
COPY files/default.conf /etc/nginx/conf.d/
COPY files/nginx.conf /etc/nginx/ngonx.conf
COPY files/supervisord.conf /etc/supervisord.conf
ADD webroot.tar /
RUN choen -R nginx:nginx /var/www/html
EXPOSE 80/tcp
ENTRYPOINT ["supervisord"]
CMD ["-c", "/etc/supervisord.conf"]