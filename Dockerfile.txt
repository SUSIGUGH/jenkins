FROM nginx
RUN mkdir -p /var/www/html
COPY ./index.html /usr/share/nginx/html/