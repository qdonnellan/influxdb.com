---
title: Installation
---

The easiest way to get started using InfluxDB is to head over to [play.influxdb.org](http://play.influxdb.org) where you can create a database and start writing data and exploring it through the administrative interface in seconds. There's no signup required. It's an open sandbox for you to play in.

Or, if you're ready to use InfluxDB in production, you may want to check out our [managed hosted InfluxDB offering](http://customers.influxdb.com).

## Ports
By default InfluxDB will use ports `8083`, `8086`, `8090`, and `8099`. Once you install you can change those ports and other options in the configuration file, which is located at either `/opt/influxdb/shared/config.toml` or `/usr/local/etc/influxdb.conf`

## Reporting

As of version 0.7.1, InfluxDB will report anonymous data once every 24 hours to m.influxdb.com. This includes the raft id (randomly generated 8 bytes), the InfluxDB version, the OS, and the architecture (amd64, ARM, etc). We don't log or track the IP Addresses that the reports are made from. This information is very helpful for our project. It lets us know how many servers are running out there in the world and, more importantly, which versions.

This is enabled by default. You can opt-out of this by editing the config file and setting `reporting-disabled = true`. However, we'd be very grateful if you keep it enabled.

## File Limits

InfluxDB can potentially have many open files. You will need to up the open file limits on your box. Pretend like we made it past 1999 and computers can actually handle more than 256 open files, and set the open file limit to `unlimited`. Basho has a nice [writeup on setting the open file limits](http://docs.basho.com/riak/latest/ops/tuning/open-files-limit/).

Replace the `riak` user with `influxdb` and you should be good to go.

## OS X

Installation of version 0.8.x on OS X is no longer supported through [Homebrew](http://brew.sh/). You will need to build from source. If that's unclear please contact us at [support@influxdb.com](mailto:support@influxdb.com).


## Ubuntu & Debian
Debian users can install by downloading the package and installing it like this:

```bash
# for 64-bit systems
wget https://s3.amazonaws.com/influxdb/influxdb_0.8.8_amd64.deb
sudo dpkg -i influxdb_0.8.8_amd64.deb

# for 32-bit systems
wget https://s3.amazonaws.com/influxdb/influxdb_0.8.8_i686.deb
sudo dpkg -i influxdb_0.8.8_i686.deb
```

Then start the daemon by running:

```
sudo /etc/init.d/influxdb start
```

## RedHat & CentOS
RedHat and CentOS users can install by downloading and installing the rpm like this:

```bash
# for 64-bit systems
wget https://s3.amazonaws.com/influxdb/influxdb-0.8.8-1.x86_64.rpm
sudo rpm -ivh influxdb-0.8.8-1.x86_64.rpm

# for 32-bit systems
wget https://s3.amazonaws.com/influxdb/influxdb-0.8.8-1.i686.rpm
sudo rpm -ivh influxdb-0.8.8-1.i686.rpm
```

Then start the daemon by running:

```
sudo /etc/init.d/influxdb start
```

<a href="getting_started.html"><font size="6"><b>Now get started!</b></font></a>
