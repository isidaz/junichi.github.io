---
layout: post
title: OS Xをzabbixの監視対象に
date: 2013-02-03 09:59:27
categories:
- pc
tags:
- ZABBIX
- OS X
---
インストールはbrewで可能。オプションでagentのインストールのみ。

    $ brew install --agent-only zabbix
    Warning: Your Xcode (4.5.2) is outdated
    Please install Xcode 4.6.
    ==&gt; Downloading http://sourceforge.net/projects/zabbix/files/ZABBIX%20Latest%20Stable/2.0.4/zabbix-2.0.4.tar.gz
    ######################################################################## 100.0%
    ==&gt; ./configure --prefix=/usr/local/Cellar/zabbix/2.0.4 --enable-agent
    ==&gt; make install
    ==&gt; Caveats
    Please read the fine manual for post-install instructions:
    http://www.zabbix.com/documentation/2.0/manual
    
    Or just use Puppet:
    https://github.com/bjoernalbers/puppet-zabbix_osx
    ==&gt; Summary

自動起動は下記サイトを参考に。

[インストールしたZabbixエージェントをOS起動のタイミングで実行 | Software - Soukaku's HENA-CHOKO Blog](http://www.downtown.jp/~soukaku/archives/2012/1205_000100.html)
