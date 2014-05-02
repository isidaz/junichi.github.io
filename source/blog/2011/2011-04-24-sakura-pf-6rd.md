---
layout: post
status: publish
published: true
title: さくらVPSでpd。6rdに対応。
date: 2011-04-24 20:04:01
categories:
- network
tags:
- 6rd
- Sakura
- VPS
- IPv6
- pf
- Firewall
- FreeBSD
---
6rdのあたりは正しいのだろうか。
<blockquote>ext_if = "em0"
ext_addr = "59.106.172.117"
tun_6rd = "stf0"

# allow services.
tcp_services = "{ 10050, 30000, smtp, http, https, domain, ntp }"
udp_services = "{ domain, ntp }"

# not deny.
set block-policy drop

scrub in all

# Default rule.
block all

# IP spoofing blocking.
antispoof log quick for $ext_if inet

# Form local is all ok.
pass quick on lo0 all

# SSH attack logging.
block in log quick on $ext_if inet proto tcp from any to $ext_if port 22

# IPv4 rules.
pass in quick on $ext_if inet proto icmp all icmp-type echoreq keep state
pass in quick on $ext_if proto tcp from any to $ext_if port $tcp_services flags S/SA keep state
pass in quick on $ext_if proto udp from any to $ext_if port $udp_services keep state

pass out quick on $ext_if inet proto icmp icmp-type 8 code 0 keep state
pass out quick on $ext_if proto tcp all modulate state flags S/SA
pass out quick on $ext_if proto {udp, icmp} all keep state

# For 6rd.
pass quick on $ext_if inet proto 41 from any to $ext_if
pass quick on $ext_if inet proto 41 from $ext_if to any

# IPv6 rules.
pass in quick on $tun_6rd proto icmp6 all
pass in quick on $tun_6rd proto tcp from any to $tun_6rd port $tcp_services flags S/SA keep state
pass in quick on $tun_6rd proto udp from any to $tun_6rd port $udp_services keep state</blockquote>
