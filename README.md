Icinga/Nagios plugin to check MDB database
==========================================

This script could be used as Icinga/Nagios check plugin to check MDB database.

This script use *mdbstat* utility to do this check.

Installation
------------

```
apt install lmdb-utils
git clone https://gogs.zionetrix.net/bn8/check_mdb.git /usr/local/src/check_mdb
mkdir -p /usr/local/lib/nagios/plugins
ln -s /usr/local/src/check_mdb/check_mdb /usr/local/lib/nagios/plugins/
echo "command[check_mdb]=/usr/local/lib/nagios/plugins/check_md" > /etc/nagios/nrpe.d/ldap-mdb.cfg
service nagios-nrpe-server reload
```


Usage
-----

```
Usage : check_mdb [-d] [-h] [-w warning] [-c critical] [options]
	-u			Sudo as specified user to run mdb_stat
	-s			Path to mdb_stat (Default : auto-detected)
	-p			Database path (Default : /var/lib/ldap)
	-w			Used pages percentage warning limit (Default: 70)
	-c			Used pages percentage critical limit (Default: 90)
	-d			Debug mode
	-h 			Show this message
```

Copyright
---------

Copyright (c) 2020 Benjamin Renard

License
-------

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License version 3
as published by the Free Software Foundation.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307, USA.

