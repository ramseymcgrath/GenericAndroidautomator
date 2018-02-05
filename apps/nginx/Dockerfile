FROM nginx:latest

LABEL maintainter = 'Ramsey McGrath <ramseymcgrath@gmail.com>'

COPY src/config/default.conf /etc/nginx/conf.d/
RUN mkdir /var/www && \
  chmod -R 744 /var/www/
EXPOSE 80