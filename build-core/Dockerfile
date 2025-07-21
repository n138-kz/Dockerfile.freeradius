FROM freeradius/freeradius-server:latest
COPY build-core/raddb/ /etc/raddb/

RUN set -x
RUN apt-get install -y postgresql
RUN sed -i 's/^\tauth = no/\tauth = yes/g' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_badpass = no/\tauth_badpass = yes/g' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_goodpass = no/\tauth_goodpass = yes/g' /etc/raddb/radiusd.conf
