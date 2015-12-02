# PowerDNS Dockerized

PowerDNS relies on the traditional role of PID 1 in reaping zombies. This container includes my [Ubuntu PPA packaging](https://launchpad.net/~danieldent/+archive/ubuntu/pidunu) of [pidunu](https://github.com/rciorba/pidunu) to handle zombies.

By default, no volumes are created by default, nor are there provisions for adjusting config files - users may not require the use of config files in their containers.

An automated build of this package is on [Docker Hub](https://hub.docker.com/r/danieldent/powerdns/).

# Example Use

    FROM danieldent/powerdns
    CMD ["/sbin/pidunu", "/usr/sbin/pdns_server",  "--no-config", "--launch=remote", "--remote-connection-string=http:url=http://example.com/jsonendpoint"]
