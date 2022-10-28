+++
title = 'Guide On Mastering DNF on Fedora'
description = 'Get to know DNF package manager on Fedora and mastering it'
tags = ['linux']
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

```Shell
tee -a /etc/dnf/dnf.conf <<EOF > /dev/null
defaultyes=True
keepcache=True
minrate=30k
EOF
```

- A lot of articles are saying to enable fastestmirror to increase speed, however it is not effective because it's sort only the fastest ping, not fastest bandwidth.
- On full configuration reference, there is `fastestmirror` option, however it is [not advisable](https://forums.fedoraforum.org/showthread.php?328191-Enable-Fastest-Mirror). `minrate` with a recommendation value of 30k is preferable.
- `max_parallel_downloads` useless if bandwidth is low. default is set to 3, max 20
- Because `keepcache` is enabled, cache can be cleaned using the command `dnf clean all`

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




