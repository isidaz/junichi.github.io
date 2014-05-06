---
status: publish
published: true
title: ひかり電話への道
date: 2008-10-13 02:27:39
categories:
- pc
tags:
- RT57i
- ひかり電話
- フレッツスクウェア
---
試したくなって申し込んだ。来週中には開通。Astriskをしこんでやる予定。

ひかり電話は接続時に1セッション必要になるらしい。つながってしまえばそのセッションは必要なくなるが。現在2セッション使っているため設定のたび1セッション切断するのもめんどうだしーということでセッションプラス。

久しぶりにフレッツスクウェアなんかに接続。RT57iに設定してみる。ルーティングの書き換え。最新情報は下記の通り。<a href="http://www.flets.com/square/routing.html">http://www.flets.com/square/routing.html</a>より。
<blockquote>220.210.194.0/25
220.210.194.160/27
220.210.199.192/27
220.210.196.0/25
220.210.196.128/26
220.210.198.0/26
220.210.199.144/28
220.210.199.208/28</blockquote>
んでもってRT57i用。
<blockquote>ip route default gateway pp 1
ip route 220.210.194.0/25 gateway pp 2
ip route 220.210.194.160/27 gateway pp 2
ip route 220.210.199.192/27 gateway pp 2
ip route 220.210.196.0/25 gateway pp 2
ip route 220.210.196.128/26 gateway pp 2
ip route 220.210.198.0/26 gateway pp 2
ip route 220.210.199.144/28 gateway pp 2
ip route 220.210.199.208/28 gateway pp 2
dns server select 1 pp 2 any .flets
dns server select 2 pp 1 any .
clear dns cache</blockquote>
申し込み。3時くらいに開通。
