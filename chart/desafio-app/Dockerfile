FROM nginx:latest

RUN addgroup --system nginx && adduser --system --no-create-home --group nginx

RUN chown -R nginx:nginx /var/cache/nginx /var/log/nginx /etc/nginx /var/tmp

RUN sed -i 's|/var/run/nginx.pid|/tmp/nginx.pid|' /etc/nginx/nginx.conf

USER nginx

EXPOSE 80


CMD ["nginx", "-g", "daemon off;"]
