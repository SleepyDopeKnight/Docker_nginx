FROM nginx

USER root

COPY ./run.sh /home/run.sh
COPY ./nginx.conf /etc/nginx/

RUN \
    useradd jojo && \
    chown -R jojo:jojo /etc/nginx/nginx.conf && \
    chown -R jojo:jojo /var/cache/nginx && \
    chown -R jojo:jojo /var/log/nginx && \
    chown -R jojo:jojo /home && \
    touch /var/run/nginx.pid && \
    chown -R jojo:jojo /var/run/nginx.pid && \
    chmod 755 bin/mount && \
    chmod 755 usr/bin/gpasswd && \
    chmod 755 usr/bin/chage && \
    chmod 755 usr/bin/expiry && \
    chmod 755 usr/bin/wall && \
    chmod 755 usr/bin/newgrp && \
    chmod 755 usr/bin/passwd && \
    chmod 755 usr/bin/chsh && \
    chmod 755 usr/bin/chfn && \
    chmod 755 bin/umount && \
    chmod 755 bin/su && \
    chmod 755 sbin/unix_chkpwd && \
    rm -rf /var/lib/apt/lists && \
    chmod +x /home/run.sh

WORKDIR /home/

USER jojo
HEALTHCHECK NONE
# run nginx as a non-daemon process
CMD ["nginx", "-g", "daemon off;"]