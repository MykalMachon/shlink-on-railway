FROM shlinkio/shlink-web-client

# install openssl
# USER root
# RUN apk add openssl

# add options for basic authentication
# RUN echo -n 'mykal' >> /etc/nginx/.httpasswd
# RUN openssl passwd -apr1 testpass >> /etc/nginx/.httpasswd 

# debu stuff
# RUN ls -la /etc/nginx/conf.d/

# append basic auth config to nginx in /etc/nginx/conf.d/default.conf
# COPY ./default.conf /etc/nginx/conf.d/default.conf

# debug stuff
RUN cat /etc/nginx/conf.d/default.conf
RUN ls -la /etc/nginx/conf.d/

# start the server as normal
ENTRYPOINT [ "/docker-entrypoint.sh", "nginx"]