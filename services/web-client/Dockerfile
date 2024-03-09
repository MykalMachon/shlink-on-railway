FROM shlinkio/shlink-web-client

# install openssl
USER root
RUN apk add openssl

# set default username/passowrd 
# THESE SHOULD NEVER BE USED; you should ALWAYS override them 
ARG USERNAME=shlink_admin
ARG PASSWORD=shlink_password 

# add basic authentication
RUN echo -n "$USERNAME:" >> /etc/nginx/.httpasswd
RUN openssl passwd -apr1 $PASSWORD >> /etc/nginx/.httpasswd 

# debu stuff
RUN ls -la /etc/nginx/conf.d/

# append basic auth config to nginx in /etc/nginx/conf.d/default.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf

# debug stuff
RUN cat /etc/nginx/.httpasswd
RUN cat /etc/nginx/conf.d/default.conf
RUN ls -la /etc/nginx/conf.d/

# start the server as normal
USER $uid