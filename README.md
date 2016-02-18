SiLK Xtensions
==============

A set of tools that augment or improve the functionality and features of SiLK (System for Internet-Level Knowledge). In the same way that all the SiLK tools are prefixed with `rw`, all silk-xtension tools are prefixed with `sx`. 

sxcleaner
---------

Retention management of SiLK data repository. A normal SiLK installation provides no means to automatically delete old network flow data. This script will delete data from the data repository, as defined by `DATA_ROOTDIR` setting in `rwflowpack.conf`. Deletion of data can be based either on a given number of days ago, or by a spesific date or timestamp. By default it outputs information and status to both STDOUT and Syslog. When running in CRON, you may specify the `-q` flag to silence the console output. If you specify the `-x` flag, you'll get a dry-run only, where date will not be deleted.

sxrepchk
--------

Check the SiLK data repository for each sensor (i.e. organization) and see if it is up to date. It basically parses the output of the `rwsiteinfo` command. If the repo data is more than an hour behind, you will see a warning. The tool can also format the output as JSON if the `--json` flag is specified.

You can easily use this tool as a status monitor. E.g. `watch -n 30 -c sxrepchk` will reload the output every 30 seconds so you can have a simple status display of the data repository.
