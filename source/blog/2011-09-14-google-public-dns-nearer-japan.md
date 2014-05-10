---
status: publish
published: true
title: Google Public DNSが日本から近くなった。
date: 2011-09-14 21:13:36 JST
categories:
- network
tags:
- Google
- DNS
- AS2519
- AS15169
---
www.google.co.jpは前からお隣さんだったが、DNSはお隣さんに設置されていなかったようで数十msecはかかってたはず。

[text]
traceroute to 8.8.8.8 (8.8.8.8), 64 hops max, 52 byte packets
1  [AS2519] 27-96-48-89.ipq.jp (27.96.48.89)  0.774 ms  0.921 ms  0.982 ms
2  [AS2519] Tok4B1.vectant.ne.jp (163.139.126.97)  7.979 ms  4.942 ms  5.974 ms
3  [AS2519] 163-139-126-126.rv.vectant.ne.jp (163.139.126.126)  5.985 ms  13.907 ms  17.985 ms
4  [AS2519] 163-139-68-53.rv.vectant.ne.jp (163.139.68.53)  13.939 ms  10.928 ms  8.952 ms
5  [AS2519] ae1.peer3.nihonbashi.vectant.ne.jp (163.139.128.194)  6.971 ms  6.942 ms  5.960 ms
6  [AS15169] 72.14.215.70 (72.14.215.70)  6.983 ms  7.870 ms  5.960 ms
7  [AS15169] 209.85.249.195 (209.85.249.195)  7.030 ms
[AS15169] 209.85.249.192 (209.85.249.192)  5.890 ms
[AS15169] 209.85.249.195 (209.85.249.195)  12.888 ms
8  [AS15169] 209.85.241.65 (209.85.241.65)  6.945 ms  9.909 ms  9.975 ms
9  [AS15169] 209.85.241.139 (209.85.241.139)  9.963 ms  8.910 ms  7.985 ms
10  [AS15169] google-public-dns-a.google.com (8.8.8.8)  9.966 ms  7.919 ms  7.968 ms
[/text]
