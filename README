backup-luks
===========

Convenient wrapper for running encrypted backups with rsync and as cronjobs.
Uses `dm-crypt`.

How to use
----------

Steps 1-3 are required only once.

1. Ensure you have a valid partition for your device

Normally you should have a partition table, if not run

```
create_partition /dev/sdb
```

(it will create a GPT table and one main partition)

2. Create a new encrypted disk

For convenience you can use

```
create_disk /dev/sdb1 /path/to/place/your/secure/luks/keys
```

you can also use stdin for the password 

```
echo "awesome_pwd" | create_disk /dev/sdb1 /path/to/place/your/secure/luks/keys
```

3. Rename `backup-example` & fill in the variables


4. Run the backup script

```
./backup-example
```

5. Optional: Setup cronjobs

Security
------------

Store your luksKeys on __secure__ folder

Requirements
------------

* __`dm-crypt`__ (Linux kernel > 2.6)
* `bash`
* `notify-send`


optional:

* `gdisk` (for the partition)
* python + gtk3 (for notification icons)
* [cronic](http://habilis.net/cronic/) (for cronjobs)


Cronjobs
--------

```
15 */2 * * * /usr/bin/cronic <path-to-repo>/backup/backup-example -c
```

(this runs the cron job every two hours)


License
-------

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
