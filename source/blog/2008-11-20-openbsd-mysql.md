---
status: publish
published: true
title: OpenBSDでMySQL
date: 2008-11-20 22:50:09 JST
categories:
- pc
tags:
- MySQL
- OpenBSD
- PHP
- phpMyAdmin
---
MySQLをPHPで使おうと。まぁphpMyAdmin入れようとしたんだけどね。はじめソースをそのまま入れたんだがどうもうまくいってないなぁ、よしpkg_addしてみよう。同じエラーか。以下のように対処。
<ul>
	<li>php.iniのsession.save_path = "/tmp"に。/var/www/tmp作成。</li>
	<li>my.cnfのmysql.sockの生成場所を/var/run/mysql/mysql.sockへと。pnp.iniの参照場所も変更。</li>
</ul>
OpenBSDのApacheは/var/wwwにchrootされているため。この方法でいいのだろうか。
