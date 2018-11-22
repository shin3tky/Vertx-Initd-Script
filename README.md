# Vert.x 3 init.d Script

This is an improved script based on the official [Vert.x 3 init.d Script](https://vertx.io/blog/vert-x-3-init-d-script/).

This script can execute the Vert.x application as a nologin user.

This script works on the CentOS 6.


## Application user

Add a user of the application.

```
$ sudo useradd -M -s /sbin/nologin appuser
```


## Configuration

Please update the settings according to your application.

|name|description|
|----|----|
|APP_ENV|application setting environment|
|APP_NAME|fat jar base name|
|APP_VER|fat jar version|
|RUN_USER|application user|
|APPLICATION_DIR|application parent directory|
|JVM_OPTS|Java VM options|


## Setup init.d script

Setup.

```
$ sudo cp MyVertxApp /etc/init.d/
$ sudo chmod +x /etc/init.d/MyVertxApp
$ sudo chkconfig --add MyVertxApp
$ sudo chkconfig MyVertxApp on
```

Start/Stop/Status.

```
$ sudo service MyVertxApp start
$ sudo service MyVertxApp stop
$ sudo service MyVertxApp status
```

