# Monitoring Plugins

A collection of monitoring plugins for Nagios/Icinga and compatible monitoring
systems.
Most plugins require the `Nagios::Plugin` perl module.

The plugins have been written at Amadeus Germany GmbH but are fairly generic.

## Plugins

### `check_memory_solaris`

Checks free memory on Solaris. Assumes perl from CSW.

### `check_nightly_reboot`

Checks if the machine is scheduled for a nightly reboot.
This plugins requires some further configuration, please take a look at
[its documentation](check_nightly_reboot/README.md).
Requires systemd.

### `check_systemd_units`

Checks that no systemd units are in `failed` state.

Requires systemd.

### `check_zfs`

Checks remaining space and status of zpools.

### `check_ntp_report_stats`

Checks reachability of an NTP server.
This is like the common `check_ntp` plugin but provides more performance data.

### `check_yaml`

Check a key to have a certain value in a yaml file.

Requires the `Yaml::Syck` perl module.

#### Example to test for the status of the last puppet run:

```sh
$ check_yaml -i /var/lib/puppet/state/last_run_summary.yaml -k resources -k failed -e 0
```

### `check_mounts`

Check for mounted filesystems/mountpoints which are not expected.

### `check_bacula`

Check the status of the last job for a bacula client.

### `check_bacula_server`

Check if the last job for any client has failed on a bacula server

### `check_nfsmounts_perfdata`

Check whether there are stale NFS mounts on the host.

### `check_log_seen_today`

Check that matching log entries have been seen today.

### `check_dkim`

Check DKIM DNS records for presence, type and public key.
Requires the `Mail::DKIM` perl module.

### `check_puppet_agent`

Check that puppet agent is not disabled.
Optionally requires the `JSON::MaybeXS` and `File::Slurp` modules, if the
message from the lockfile is to be parsed.

### `check_atlassian`

Check time until license expiration of Atlassian tools.
Requires the `LWP::Simple` (`libwww-perl`) and `HTML::Parser` perl modules

### `check_http_health`

Check the health of a HTTP endpoint with HAProxy behaviour
(200 -> OK, 500 -> CRITICAL, rest -> UNKNOWN)
Requires the `LWP::Simple` perl module.

### `check_apparmor`

Check status of AppArmor on the machine.

### `check_needrestart`

Check if daemon have to be restarted after a library upgrade.

Requires the [`needrestart`](https://github.com/liske/needrestart) package.

Note: From `needrestart` version 2.1 and upwards you can use its native nagios
plugin mode (pass `needrestart -p`)

## License


* Default: MIT
* check_memory_solaris: GPL-2.0+
* check_nfsmounts_perfdata: GPL-3.0+
* check_apparmor: GPL-2.0

For the authorative information look at the plugin source itself.
