FROM tzumby/openresty-waf

# forward nginx access and error logs to stdout and stderr of the ingress
# controller process
RUN ln -sf /proc/1/fd/1 /var/log/nginx/access.log \
	&& ln -sf /proc/1/fd/2 /var/log/nginx/error.log

RUN mkdir -p /etc/nginx/conf.d

COPY nginx-ingress nginx/ingress.tmpl nginx/nginx.conf.tmpl /

ENTRYPOINT ["/nginx-ingress"]
