# Configuring the PHP - Xdebug - Webgrind combo

## Overview

1. [Make sure apache and php are properly installed](#1-make-sure-apache-and-php-are-properly-installed)
2. [Install Xdebug](#2-install-xdebug)
3. [Configure Xdebug](#3-configure-xdebug)
4. [Install Webgrind](#4-install-webgrind)
5. [Configure Webgrind](#5-configure-webgrind)
6. [Secure Webgrind](#6-secure-webgrind)

## 1. Make sure apache and php are properly installed
**Not much to say about that...**

## 2. Install Xdebug
`pecl install xdebug`

## 3. Configure Xdebug
1. Get [the unofficial config file](http://gggeek.altervista.org/2007/11/26/the-completely-unofficial-xdebugini/)
2. Add the code to your `php.ini` file
3. Check if the path to the xdebug so file is correct `extension=xdebug.so`
4. Enable the trigger `xdebug.profiler_enable_trigger=1` OR enable always **(no good idea)** `xdebug.profiler_enable=1`

## 4. Install Webgrind
1. Get the latest zip from [google code](http://code.google.com/p/webgrind/downloads/list)
2. Unpack it

## 5. Configure Webgrind
Check if the settings in config.php are correct

## 6. Secure Webgrind
### Create a .htaccess file in the webgrind directory
	AuthName "Beveiligde zone"
	AuthType Basic
	AuthUserFile /path/to/parent/dir/.htpasswd
	Require valid-user

### Create a .htpasswd file in the webgrind's parent directory
the file must contain the user/pass combo(s) for webgrind
