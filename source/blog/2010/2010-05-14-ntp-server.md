---
layout: post
status: publish
published: true
title: NTPサーバーを作りたい
date: 2010-05-14 00:10:45
categories:
- electronics
tags:
- AVR
- NTP
- TCP/IP
---
NTP専用で、stratum 1を。GPS使用します。つまり下記の様な製品。
<ul>
	<li><a href="http://www.shoshin.co.jp/c/endrun/index.html">タイムサーバー CDMA GPS NTP SNTP ntpd PTP 1588 ネットワーク</a></li>
	<li><a href="http://www.symmetricom.com/products/ntp-servers/">Network Time Protocol (NTP) Time Servers : Symmetricom</a></li>
</ul>
FreeBSDが動くPCを使えば簡単にできるでしょう。
<ul>
	<li><a href="http://www.meinberg.de/english/products/gps170pci.htm">GPS PCI Radio Clock GPS170PCI</a></li>
</ul>
PCIにさせるGPSなんて有ったんですね。または<a href="http://www.pcengines.ch/alix.htm">PC Engines ALIX system boards</a>が何枚か有るのでこれが一番簡単。

しかし、これではつまらないなー。ラックマウントして時刻がLCDで表示できるとかっこいい。まっさきにArduinoを思いついた。クライアントとしての事例は見かけるがサーバーと動かせるのかはわからない。TCP/IPをどう実装するのかという問題も。
<ul>
	<li><a href="http://www.switch-science.com/products/detail.php?product_id=16">スイッチサイエンス/商品詳細 TCP/IPハードウェア処理チップ「W5100」</a></li>
</ul>
なんだやっぱりあるのか。ということはAVRとの組み合わせで行ける。POP3を動作させている例も見つけた。これぞまさに作る?
