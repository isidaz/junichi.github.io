---
title: OmniOSでNetatalk 3.1.0をビルド
date: 2013-11-25 19:00:00 JST
tags:
- OmniOS
- Netatalk
---

OmniOSでNetatalk3.1.0をビルドした。pkgで3.0.5は有ったのだが最新を使いたいので。
以下のサイトを参考に必要なパッケージをインストールしconfigure make。

* [Install Netatalk 3.0.6 on OpenIndiana 151a8 - Netatalk Wiki](http://netatalk.sourceforge.net/wiki/index.php/Install_Netatalk_3.0.6_on_OpenIndiana_151a8 "Install Netatalk 3.0.6 on OpenIndiana 151a8 - Netatalk Wiki")
* [omnios-build/build/netatalk/build.sh at uulm.mawi · stefri/omnios-build · GitHub](https://github.com/stefri/omnios-build/blob/uulm.mawi/build/netatalk/build.sh "omnios-build/build/netatalk/build.sh at uulm.mawi · stefri/omnios-build · GitHub")

configureは通るのだが、makeでエラーが出たため下記ファイルの一部を削除。

* /usr/include/amd64/sys/privregs.h
* [Re: [OmniOS-discuss] non-amd64 code depends on amd64 privileged header!](http://www.mail-archive.com/omnios-discuss@lists.omniti.com/msg00812.html "Re: [OmniOS-discuss] non-amd64 code depends on amd64 privileged header!")


make時にwarningが出ているが、利用に問題は起きていない。


