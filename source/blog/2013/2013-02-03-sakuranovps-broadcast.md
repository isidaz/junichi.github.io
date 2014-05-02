---
layout: post
title: さくらのVPSで飛んでくるブロードキャストパケット
date: 2013-02-03 10:31:00
categories:
- diary
tags:
- VPS
- さくらのVPS
- さくら
- Dropbox
---
WindowsとDropboxが多い。

    Feb 3 08:00:02 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.73:17500 255.255.255.255:17500 in via em0
    Feb 3 08:00:02 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.73:17500 133.242.139.255:17500 in via em0
    Feb 3 08:00:08 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.24:138 133.242.139.255:138 in via em0
    Feb 3 08:00:17 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.57:17500 255.255.255.255:17500 in via em0
    Feb 3 08:00:17 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.57:17500 133.242.139.255:17500 in via em0
    Feb 3 08:00:27 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.80:17500 255.255.255.255:17500 in via em0
    Feb 3 08:00:27 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.80:17500 133.242.139.255:17500 in via em0
    Feb 3 08:00:32 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.73:17500 255.255.255.255:17500 in via em0
    Feb 3 08:00:32 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.73:17500 133.242.139.255:17500 in via em0
    Feb 3 08:00:47 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.57:17500 255.255.255.255:17500 in via em0
    Feb 3 08:00:47 ns3 kernel: ipfw: 900 Deny UDP 133.242.138.57:17500 133.242.139.255:17500 in via em0
    Feb 3 08:00:49 ns3 kernel: ipfw: 900 Deny UDP 133.242.139.205:137 133.242.139.255:137 in via em0
