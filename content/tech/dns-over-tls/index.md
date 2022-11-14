+++
title = 'DNS Over TLS to Prevent ISP from Blocking Websites'
description = 'Encrypt DNS queries for a more free internet 🔓'
techtags = ['linux']
date = 2022-11-14T20:38:38+07:00
+++

# DNS Over TLS

Definition from [Cloudflare](https://www.cloudflare.com/learning/dns/dns-over-tls/):
>DNS over TLS, or DoT, is a standard for encrypting DNS queries to keep them secure and private. DoT uses the same security protocol, TLS, that HTTPS websites use to encrypt and authenticate communications. DoT adds TLS encryption on top of the user datagram protocol (UDP), which is used for DNS queries.

## systemd-resolved

If you are using Linux OSs with systemd, using this service will allow us to use DNS over TLS on our system.

Here's my config files for `/etc/systemd/resolved.conf`

```sh
DNS=1.1.1.1#cloudflare-dns.com 1.0.0.1#cloudflare-dns.com 606:4700:4700::1111#cloudflare-dns.com 2606:4700:4700::1001#cloudflare-dns.com
FallbackDNS=9.9.9.9#quad9.net 149.112.112.112#quad9.net 2620:fe::fe#quad9.net 2620:fe::9#quad9.net
Domains=~.
DNSSEC=yes
DNSOverTLS=yes
```

> Personally I use cloudflare with quad9 as fallback. You can pick and choose how you want.

To restart the services, run

```sh
sudo systemctl restart systemd-resolved
sudo systemctl restart NetworkManager
```

Check status

```sh
resolvectl status
```

Test connection at <https://1.1.1.1/help>



# DNS over HTTPS

Basically the difference is, instead of encrypting DNS queries directly over UDP, <abbr title="DNS over HTTPS">DoH</abbr> encrypt from the HTTP or HTTP/2 protocol. Most major browsers actually have this feature built-in. On firefox:

{{<figure src="browser.png" alt="DNS over HTTP on browser">}}

However, by using DNS over TLS with systemd-resolved, we are encrypting our DNS queries system-wide, rather than only the browser.

# References

- <https://medium.com/@jawadalkassim/enable-dns-over-tls-in-linux-using-systemd-b03e44448c1c>
- <https://dns.sb/guide/dot/linux/#debian-and-most-popular-linux-distributions>
- <https://www.cloudflare.com/learning/dns/dns-over-tls/>
