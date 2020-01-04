## For setup Codignitor project.

### for setup database

> application/config/database.php
```
  ...
  
  $db['default'] = array(
	'dsn'	=> '',
	'hostname' => 'localhost',
	'username' => 'root',
	'password' => ' ',
	'database' => 'test',
	'dbdriver' => 'mysqli',
	'dbprefix' => '',
  ...
```
### for setup autoload library

> application/config/autoload.php
```
 $autoload['libraries'] = array('database', 'email', 'session');
```

### for setup new routes

> application/config/routes.php

```
$route['default_controller'] = 'welcome';
$route['custom_controller'] = 'custome';
```
