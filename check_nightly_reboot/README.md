# `check_nightly_reboot`

Checks if the machine is scheduled for a nightly reboot.
It assumes a systemd timer is running, which will trigger the reboot.

An example unit file is provided in [`nightly-reboot.timer`](nightly-reboot.timer).
