This image provides a streamlined [ApacheDS](http://directory.apache.org/apacheds/) server, which implements both LDAP v3 and Kerberos (and more).

## Getting Started

All of the default ports [documented here](http://directory.apache.org/apacheds/advanced-ug/1.2-network.html) are exposed by this image, but most often you will just map the LDAP port (10389 for ApacheDS). For example, to get up and running quickly launch a container using:

    docker run -d --name ads -p 389:10389 itzg/apacheds

You can then configure and manage ApacheDS using [Apache Directory Studio](http://directory.apache.org/studio/) by creating a new LDAP server connection like:

![Network Parameters](http://i.imgur.com/7vfSsbq.png)

![Authentication](https://i.imgur.com/d6EBYp7.png)

## Volumes

The image starts a container using the default instance configuration that comes with the distribution; however, the instances are placed under the Docker volume /ads where the default is at the path /ads/default. As such, those files are persistable and configurable, but the default admin DN "uid=admin,ou=system" and the default password is "secret".
