+++
title = 'Guide on mastering DNF on Fedora'
description = 'General knowledge on DNF package manager for day-to-day usage'
techtags = ['linux']
date = 2022-10-28T07:39:43+07:00
+++

# References

- [Official documentation](https://dnf.readthedocs.io/en/latest/index.html) with full commands and configuration references.
- [Commands references from Oracle](https://docs.oracle.com/en/operating-systems/oracle-linux/software-management/sfw-mgmt-DNFCommandReference.html#dnf-command-ref)

# Quick Knowledge

- DNF or Dandified YUM is a successor of YUM package manager.
- Global configuration is stored at `/etc/dnf/dnf.conf`
- All *.repo files is found under `/etc/yum.repos.d`

# Useful configuration

Here is my own config:

```shell
tee -a /etc/dnf/dnf.conf <<EOF > /dev/null
defaultyes=True
keepcache=True
minrate=30k
EOF
```

## Known options

### `defaultyes`

So you don't have to type "Y" before pressing Enter.

### `fastestmirror`

A lot of articles are saying to enable `fastestmirror` to increase speed, however it is not effective because it's sort only the fastest ping, not fastest bandwidth.

Using `minrate` is [more advisable](https://forums.fedoraforum.org/showthread.php?328191-Enable-Fastest-Mirror).

### `minrate`

This is an alternative of using `fastestmirror`. The recommendation value is 30k.

### `max_parallel_downloads`

Useless if bandwidth is low. default is set to 3, max 20. My own bandwidth here in Indonesia is 10Mbit (I know it's super slow). So I don't use it.

### `keepcache`

Self explanatory. Keep in mind to clean cache occasionaly with `dnf clean all`

# Important Commands

I use a lot of shorthands, such as in for install.

- `dnf in` (install)
- `dnf rm` (remove)
- `dnf up` (upgrade)
- `dnf search`
- `dnf autoremove`
- `dnf dsync` (check for broken dependencies)
- `dnf hist userinstalled` (history of user installed packages)
- `dnf clean all` (remove cache)
