# mysql
Basic settings for mysql;

### Setup a new user and dbeaver connection bash script
```sh
#! /bin/bash

newUser='testuser'
newDbPassword='testpwd'
newDb='testdb'
host=localhost
#host='%'
 
commands="CREATE DATABASE \`${newDb}\`;CREATE USER '${newUser}'@'${host}' IDENTIFIED BY '${newDbPassword}';GRANT USAGE ON *.* TO '${newUser}'@'${host}' IDENTIFIED BY '${newDbPassword}';GRANT ALL privileges ON \`${newDb}\`.*
TO '${newUser}'@'${host}';FLUSH PRIVILEGES;"

echo "${commands}" | /usr/bin/mysql -u root -p
```
