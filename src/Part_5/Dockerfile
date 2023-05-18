FROM nginx

USER root

COPY ./run.sh /home/run.sh
COPY ./main.c /home/main.c
COPY ./nginx.conf /etc/nginx/
		
RUN apt update && \
    apt install -y spawn-fcgi && \
    apt install -y libfcgi-dev && \
    apt install -y gcc && \
    useradd jojo && \
    chown -R jojo:jojo /etc/nginx/nginx.conf && \
    chown -R jojo:jojo /var/cache/nginx && \
    chown -R jojo:jojo /home && \
    touch /var/run/nginx.pid && \
    chown -R jojo:jojo /var/run/nginx.pid && \
    chmod 777 bin/mount && \
    chmod 777 usr/bin/gpasswd && \
    chmod 777 usr/bin/chage && \
    chmod 777 usr/bin/expiry && \
    chmod 777 usr/bin/wall && \
    chmod 777 usr/bin/newgrp && \
    chmod 777 usr/bin/passwd && \
    chmod 777 usr/bin/chsh && \
    chmod 777 usr/bin/chfn && \
    chmod 777 bin/umount && \
    chmod 777 bin/su && \
    chmod 777 sbin/unix_chkpwd && \
    rm -rf /var/lib/apt/lists && \
    chmod +x /home/run.sh

WORKDIR /home/

USER jojo
HEALTHCHECK NONE
CMD ["./run.sh"]
