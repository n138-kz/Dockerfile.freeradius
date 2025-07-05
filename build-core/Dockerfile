FROM freeradius/freeradius-server:latest
COPY build-core/raddb/ /etc/raddb/

RUN set -x
RUN sed -i 's/^\tauth = no/\tauth = yes' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_badpass = no/\tauth_badpass = yes' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_goodpass = no/\tauth_goodpass = yes' /etc/raddb/radiusd.conf
