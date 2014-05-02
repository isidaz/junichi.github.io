---
layout: post
status: publish
published: true
title: Interlinkでパケットロス1
date: 2010-05-14 03:19:39
categories:
- network
tags:
- fping
- ping
- smokeping
- nuttcp
- INTERLINK
---
<a href="http://www.junkai.org/blog/wp-content/uploads/2010/05/202_61_20_217_last_10800.png"><img class="alignnone size-medium wp-image-438" title="202_61_20_217_last_10800" src="http://www.junkai.org/blog/wp-content/uploads/2010/05/202_61_20_217_last_10800-300x135.png" alt="" width="300" height="135" /></a>

2セッション張ってhi-hoから観測。

smokepingではパケットロスが確認できるが、シェルから送っても確認が出来ない。smokepingが発行しているリクエストは

/usr/local/sbin/fping -C 20 -q -B1 -r1 -i10 202.61.20.219

てな感じ。smokeping --debugで確認できます。
<ul>
	<li>-C 20 20回繰り返す</li>
	<li>-q 個々の結果を表示しない</li>
	<li>-B1</li>
	<li>-r1 リトライする回数</li>
	<li>-i10 10msecおきにpingを実行</li>
</ul>
B1がよく分からない。r1が応答かえってこなかった場合のリトライ回数でこれかな?が、いじってるうちに経路が変わりパケットロスがなくなったとさ。うやむやになった。

nuttcp -i1 -u -vv 202.61.20.219

これで計測してみた結果も多くて4%程度のロスが発生していたが、0%になった。
