---
status: publish
published: true
title: 温度が異常な値となる対応。
date: 2012-07-30 21:32:38
categories:
- Server
tags:
- ZABBIX
- USBRH
- awk
---
暑いですね。今年の室温は一体何度まで上がるのでしょうか。

たまにusbrhが異常な状態となり、-40度とか言った値がzabbixに取り込まれてしまうことがあった。そのたびにsqlで削除していたんだが面倒くさい。根本から対処。
<blockquote>crontab -e
*/1 * * * * /usr/local/bin/usbrh | awk '/^[0-5]/ { print $0 }' &gt; /tmp/usbrh</blockquote>
先頭の値は気温です。室内なので氷点下になることも60度以上になることもないだろうと言うことで。
