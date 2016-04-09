## Rsyslog Dockerfile

Rsyslog running in a linux container as a server, listening on 514 (tcp and udp), and writing to /var/log/syslog.

### Usage

This container will listen on 514/udp, and 514/tcp and write it to /var/log/syslog.

For cli creation

    docker run --name rsyslog --rm  -p 514:514/udp -p 514:514  robbert229/rsyslog -v "./syslog:/var/log/syslog"


Or For docker-compose

    version: '2'
    services:
      rsyslog:
        image: robbert229/rsyslog
        ports:
        - 514:514/udp
        - 514:514
        volumes:
        - "./syslog:/var/log/syslog"

