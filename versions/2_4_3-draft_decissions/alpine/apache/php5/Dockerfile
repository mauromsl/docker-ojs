FROM birkbeckctp/ojs:2_4_3-0

LABEL maintainer="Open Library of Humanities <support@openlibhums.org>"
WORKDIR /var/www/html
RUN apk add --no-cache curl patch
RUN curl https://raw.githubusercontent.com/mauromsl/OJS-Draft-Editorial/master/patches/editorial_decision_draft.patch > /tmp/editorial_decision.patch
RUN patch -p1 < /tmp/editorial_decision.patch


VOLUME [ "/var/www/files", "/var/www/html/public" ]

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]
