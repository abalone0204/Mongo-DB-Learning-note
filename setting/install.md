# On Linux

- distribution: Ubuntu

## Install

- Import the public key used by the package management system.:`sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10`

- Create a list file for MongoDB: `echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list`

- Reload local packages' database: `sudo apt-get update`

- Install mongoDB package: `sudo apt-get install -y mongodb-org`

> Datafiles stored in `/var/lib/mongodb`
> Logfiles stored in `/var/log/mongodb`

## Run

- `sudo service mongod start`

- Check `/var/log/mongodb/mongod.log`:

- Run `mongo`

### optional

```error
Failed global initialization: BadValue Invalid or no user locale set. Please ensure LANG and/or LC_* environment variables are set correctly.
```

- `locale-gen en_US.UTF-8` `export LC_ALL=C`


> Stop: `sudo service mongod stop`
> Restart: `sudo service mongod restart`

```
[initandlisten] waiting for connections on port <port>
```

- `<port>` is the port configured in `/etc/mongod.conf`, 27017 by default.

## Link

- [MongoDB Doc](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/)

