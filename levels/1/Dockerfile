FROM nginx
COPY ./ /usr/share/nginx/html

# Add PHP
RUN apt-get update && apt-get install -y \
  php5-common \
  php5-cli \
  php5-fpm
RUN rm -v /etc/php5/fpm/pool.d/www.conf
ADD www.conf /etc/php5/fpm/pool.d/www.conf

# Configure NGINX
RUN usermod -aG www-data nginx
RUN rm -v /etc/nginx/conf.d/default.conf
ADD default.conf /etc/nginx/conf.d/

RUN apt-get autoremove -y
RUN apt-get clean -y

CMD service php5-fpm start && nginx && tail -f /usr/share/nginx/error.log
