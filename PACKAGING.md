# Release packaging reminders

## Context
This repo provides a set of scripts for Nagios/Icinga/Centreon platforms to monitor more things.<br/>
However, most of the time, the target machines are managed using different tools and are favoring the distribution's package manager.<br/>
To help with this, the releases can contain a package in addition to the source release to offer this option.

## DEB package
This repo is configured to help generate a DEB package.<br/>
As there is not yet a CI on the GitHub repo to produce all the deliverables for the release, this documentation highlights the steps to do it manually.

### Pre-requisites
In order to successfully generate a package, you need:
* a Debian or Debian-like machine (to have most of the tools already here to deal with DEB packages)
* have the **debhelper** package installed for the few tools not present by default on Debian distros
* have a clone of the GitHub repo
* ensure that some packaging config are not executable:
```
 chmod -x debian/monitoring-plugins-amadeus.*
```

### Packaging steps

1. Update the **debian/changelog** file (follow the formatting if you do it manually)
2. Run the packaging command:
```
 debuild -us -uc
```
3. Use the *.tar.xz to also generate a *.zip archive
4. Commit and tag the changes to the repo
5. Push the commit & tag + upload all the artifacts of the release