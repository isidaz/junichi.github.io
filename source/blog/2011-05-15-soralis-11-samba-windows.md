---
status: publish
published: true
title: Soralis 11のsambaにWindows 7から接続できな
date: 2011-05-15 11:06:40
categories:
- pc
tags:
- samba
- Soralis
- Windows 7
---
正確には接続できないではなく、何回もパスワードを入れたりしてると繋がる。しばらく放置していたのだが、面倒なので直す。下記サイトより。

<a href="http://yonitg.com/solution-for-windows-7-samba-connection-problem/">Solution for Windows 7 samba connection problem | Linux Admin Steps Into Management</a>

ローカルポリシー、セキュリティオプション、ネットワークセキュリティ:LAN Manager認証レベルのプロパティの順で辿り、値を「LMとNTLM応答を送信する」に変更。
