---
layout: post
title: "AP9630をSmartUPSに装着した"
published: true
---

UPSの状態監視のためにAP9630をヤフオクで購入。7500円でした。

<a href="http://www.flickr.com/photos/jun_/11381666536/" title="APC AP9630 Network Management Card by Ishida Junichi, on Flickr"><img src="http://farm4.staticflickr.com/3767/11381666536_8c6485269e.jpg" width="500" height="333" alt="APC AP9630 Network Management Card"></a>

* 初期状態ではtelnet、httpでアクセスが可能。
* ログインはapc,apcで可能
* DHCPでアドレス取得になってるのでリース状態を調べる
* 後は見れば分かる

windowsからファームアップデートを実施。webの見た目ががらっと変わった。

<a href="http://www.flickr.com/photos/jun_/11382366836/" title="96e58d6360836e0d171faaffcdf544db by Ishida Junichi, on Flickr"><img src="http://farm4.staticflickr.com/3673/11382366836_680c639017.jpg" width="500" height="277" alt="96e58d6360836e0d171faaffcdf544db"></a>

今まではAP9620 Legacy Communication Cardを使ってた。SMT1000Jを買ってFreeBSDのapcupsdから
制御しようとしたんだが、プロトコルが変更されたらしく最初からついてるUSBポートは使えない。
FreeBSDのapcupsdから制御したければAP9620をつけてRS232接続するしかなかった。
最初からAP9630を買っとけば良かったんだろうな。

<a href="http://www.flickr.com/photos/jun_/11381725914/" title="AP9620 Legacy Communication Card by Ishida Junichi, on Flickr"><img src="http://farm4.staticflickr.com/3693/11381725914_c05e77dddf.jpg" width="500" height="333" alt="AP9620 Legacy Communication Card"></a>


