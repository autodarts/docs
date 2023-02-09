FROM nginx:alpine
COPY .docker/nginx/default.conf /etc/nginx/templates/default.conf.template
COPY static /usr/share/nginx/html/static
COPY public /usr/share/nginx/html