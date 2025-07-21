FROM freeradius/freeradius-server:latest
COPY build-core/raddb/ /etc/raddb/

RUN set -x
RUN apt-get update
RUN apt-get install -y postgresql
RUN ln -s /etc/freeradius/mods-available/sql /etc/freeradius/mods-enabled/sql
RUN sed -i 's/^\tauth = no/\tauth = yes/g' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_badpass = no/\tauth_badpass = yes/g' /etc/raddb/radiusd.conf
RUN sed -i 's/^\tauth_goodpass = no/\tauth_goodpass = yes/g' /etc/raddb/radiusd.conf
RUN sed -i 's/dialect = .*/dialect = "postgresql"/g' /etc/freeradius/mods-available/sql
RUN cat /etc/freeradius/mods-available/sql | grep 'dialect = '
