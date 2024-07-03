FROM ubuntu:latest
RUN apt-get update && apt-get install -y supervisor
RUN mkdir -p /var/log/supervisor
RUN apt install -y nginx
RUN apt-get install php8.3-fpm -y
RUN rm /etc/nginx/sites-enabled/default 
RUN rm /etc/supervisor/supervisord.conf
# COPY index.php /var/www/html
# COPY nginx.conf /etc/nginx/conf.d/
# COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
EXPOSE 80
CMD ["/usr/bin/supervisord","-c","/etc/supervisor/conf.d/supervisord.conf"]
#https://docs.docker.com/config/containers/multi-service_container/


docker run -d -v ./supervisord.conf:/etc/supervisor/conf.d/supervisord.conf -v ./index.php:/var/www/html/index.php -v ./nginx.conf:/etc/nginx/conf.d/ -p 80:80  nginx-volume2

