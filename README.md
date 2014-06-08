mayfly-environment-registrar
============================

This is part of [mayfly](https://github.com/bewt85/mayfly) which demonstrates the 
concept of testing groups of versions of services in short lived virtual environments.

This is a docker container which uses incrond to monitor `/etc/mayfly/environments/` for changes. 
If it finds a new or changed environment configuration file, it publishes the changes to etcd which 
are picked up by [haproxy_updater](https://github.com/bewt85/mayfly-haproxy-updater) which updates 
[haproxy](https://github.com/bewt85/docker-haproxy) in turn.

You can build your own versions of the container by setting the following environment variable 
to your docker index username (if you don't it uses mine) and running this bash script:

```
export DOCKER_ACCOUNT_NAME=<your_name>
sudo -E ./build.sh
```
