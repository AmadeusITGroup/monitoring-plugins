# Monitoring Plugins

A collection of monitoring plugins for Nagios/Icinga and compatible monitoring
systems.
Most plugins require the `Nagios::Plugin` perl module.

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

### `check_ntp_amadeus`

Checks reachability of an NTP server.
This is like the common `check_ntp` plugin but provides more performance data.

## License

Default: MIT
check_memory_solaris: GPL-2.0+
