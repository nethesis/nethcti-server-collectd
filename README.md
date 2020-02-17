# nethcti-server-collectd

This is the [Collectd](https://collectd.org/) plugin for [nethcti-server](https://github.com/nethesis/nethcti-server) project.

## Collected data

- Memory usage
- Number of:
  - websocket connected users
  - tcp connected users
  - total configured users
  - calls
  

## How to install

1. copy `nethcti-server.conf` into `/etc/collectd.d/`:
```bash
cd /etc/collectd.d && wget https://raw.githubusercontent.com/nethesis/nethcti-server-collectd/master/nethcti-server.conf
```
2. edit `/etc/collectd.d/nethcti-server.conf` with the correct values
3. set permission of `/etc/collectd.d/nethcti-server.conf`:
```bash
chmod 600 /etc/collectd.d/nethcti-server.conf
```
4. copy `nethcti-server.py` into `/usr/lib/python2.7/site-packages`:
```bash
cd /usr/lib/python2.7/site-packages && wget https://raw.githubusercontent.com/nethesis/nethcti-server-collectd/master/nethcti-server.py
```
5. restart collectd daemon
```bash
systemctl restart collectd
```

## Configuration

The plugin configuration is into `/etc/collectd.d/nethcti-server.conf`:

- *Host:* the machine to be analized
- *Debug:* if "True" it writes into the `/var/log/messages`
- *DB_Host, DB_User, DB_Password, DB_Name:* data about `asteriskcdrdb.cdr` database table
