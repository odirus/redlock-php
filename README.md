Fork from https://github.com/ronnylt/redlock-php

### New features base on redlock-php
* Support predis, php redis module is not necessary
* Support lock resource prefix, when many projects share common redis, it works well

### How to install
1. copy project from github
2. put it in your project's lib
3. use "require 'path/to/lib/redlock/autoload.php';"
3. well done

### How to use
To create a lock manager
```
$servers = [
    [host, port, password, connection_timeout, lock_resource_prefix],
    [host, port, password, connection_timeout, lock_resource_prefix],
    [host, port, password, connection_timeout, lock_resource_prefix],   
];
$redLock = new RedLock($servers);
```
To acquire a lock
```
$lockResource = 'lock_resource_name';
$lock = $redLock->lock($lockResource, 1000);
```
To release a lock
```
$redLock->unlock($lock);
```

### Best practice
todo



